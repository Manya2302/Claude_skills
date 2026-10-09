# CLAUDE.md — Agent System Instructions & Engineering Standards

> **Role & Mindset:** Principal Software Engineer, Systems Architect, and Security Specialist.  
> **Core Directives:** Produce 100% complete, production-ready code with zero placeholders. Verify every change with automated tests and builds before reporting completion.

---

## 1. Project Overview & Architecture

**Interceptor** is a high-performance internal API discovery and reverse-engineering platform. It captures, decrypts, and classifies web traffic via browser automation (Patchright), derives minimal required authentication, and generates fully typed JSON proxy domain plugins.

### Architectural Philosophy: The Browser is the API Client
- **Traffic Capture First:** Use `browserFetch` and WebSocket streaming to observe live requests.
- **Auth Elimination:** Systematically eliminate unnecessary headers, cookies, and tokens down to the strict minimum credential set.
- **Session Persistence:** Store active credentials inside `GenericSessionManager`.
- **Throttled Verification:** Validate endpoints last using `rateLimitedFetch` with defensive backoff.

### Monorepo Workspace Structure

```
├── apps/
│   ├── api/                   # Hono API server with WebSockets & streaming (@interceptor/api)
│   └── web/                   # Next.js frontend UI dashboard (@interceptor/web)
├── packages/
│   ├── browser/               # Patchright automation & transport classifier (@interceptor/browser)
│   ├── shared/                # Shared types, Zod schemas, debug logging (@interceptor/shared)
│   ├── test-server/           # Mock target websites (port 4444) for discovery validation
│   └── db/                    # Drizzle ORM + TimescaleDB integration (optional)
├── domains/
│   └── <name>/                # Generated domain plugins (JSON proxy routes)
│       └── boardshop/         # Reference domain with all transport implementations
├── services/
│   └── python/                # Python worker for native IPC bridges
└── scripts/
    └── ci-local.sh            # Local continuous integration test suite
```

---

## 2. Essential Commands Matrix

### Development & Service Lifecycle
```bash
# Start all services concurrently (API: 3001, Web: 3000)
pnpm dev

# Run individual workspaces
pnpm --filter @interceptor/api dev        # API server only
pnpm --filter @interceptor/web dev        # Web frontend only
pnpm --filter @interceptor/test-server start  # Mock target server on port 4444

# Build production artifacts
pnpm build
pnpm --filter @interceptor/api build
```

### Quality Assurance, Testing & Validation
```bash
# Run full local CI suite (MANDATORY before committing)
./scripts/ci-local.sh

# Unit & Integration Tests (Vitest)
pnpm test                                 # Run all test suites
pnpm test packages/browser                # Test specific package
pnpm test -- -t "session harvest"         # Run tests matching pattern
pnpm test:watch                           # Interactive watch mode

# Static Analysis & Type Checking
pnpm typecheck                            # Run TypeScript compiler checks (tsc --noEmit)
pnpm lint                                 # Biome linter check
pnpm format                               # Biome auto-formatting
pnpm lint:fix                             # Auto-apply safe linter fixes
```

### Dependency & Workspace Management
```bash
pnpm install --frozen-lockfile            # Clean, deterministic install
pnpm dedupe                               # Deduplicate shared dependencies
pnpm recursive exec -- <command>          # Execute command across all packages
```

---

## 3. Agent Operating Protocol (Rules of Engagement)

When acting on this repository, you must adhere strictly to these operational guardrails:

### A. Plan & Understand Before Executing
1. Inspect the workspace, identify existing patterns, and trace data flow before editing.
2. Outline a concise step-by-step plan for complex multi-package changes.
3. Keep modifications surgical: avoid unnecessary refactorings or rewriting working code.

### B. Zero-AI Slop & Absolute Code Completeness
- **NO Placeholders:** Never output `// TODO: implement later`, `/* logic here */`, or empty function stubs. Every function and route must be fully implemented.
- **NO Swallowed Errors:** Never use empty `catch {}` blocks. Always log structured context or rethrow domain-specific typed errors.
- **NO `any` Types:** TypeScript strict mode is enabled. Use strict interfaces, generics, or `unknown` with runtime Zod parsing.

### C. Verification Rule (Empirical Proof)
- Never assume code works.
- Always execute tests (`pnpm test`), typecheck (`pnpm typecheck`), and lint (`pnpm lint`) after making changes.
- Ensure terminal commands succeed with exit code `0` before declaring a task complete.

### D. Code Ownership & First-Principles Fixes
- **We own ALL code:** packages, apps, domains, scripts, test-servers, and configs.
- When an issue arises, fix it at the root cause. Never apply band-aids, dummy mock values, or suppress lint warnings.
- Delete obsolete code and rename identifiers freely to maintain architectural clarity.

---

## 4. Key Architecture & Endpoints

### Runtime Interception Channels
- **Browser WebSocket Stream:** `ws://localhost:3001/browser/stream?profile=<domain>&url=<target>`
- **Live Traffic Capture:** `GET /browser/traffic` *(only active when WebSocket client is connected)*
- **Domain API Proxy Route:** `GET /api/<domain>/<path>`
- **Debug Trace Logging:** `import { DEBUG } from "@interceptor/shared"` → outputs to `/tmp/interceptor-debug/`

### Reference Target Sites (Port 4444)
Use `packages/test-server` sites to validate transport classifiers:
- `boardshop`: Embedded JSON and server-rendered data extraction.
- `liveboard`: WebSocket frames with binary Protocol Buffers (`protobuf`).
- `streamshop`: GraphQL queries and HTTP Live Streaming (`HLS`) playlists.
- `databoard`: gRPC-Web binary encodings.

---

## 5. Domain Plugin Development Protocol

When creating or maintaining domain plugins in `domains/<name>/`:

1. **Discovery Phase:**
   - Launch browser traffic capture: curl-alone will miss client-side hydration requests and WebSockets.
   - Classify all transport types (XHR, fetch, SSE, GraphQL, WebSocket).
2. **Minimization Phase:**
   - Strip headers one-by-one to find minimal valid auth requirements.
   - Test without cookies, user-agent overrides, and referrers.
3. **Registration:**
   - Register the new domain plugin in `register-domains.ts`.
   - Verify all routes return strictly formatted JSON responses under `/api/<domain>/*`.
4. **Reference Implementation:**
   - Always reference `domains/boardshop/` as the canonical blueprint for transport handlers and error recovery.

---

## 6. Worktree & Multi-Agent Safety Rules

If executing inside an isolated worktree (`pwd` contains `/tmp/interceptor-worktrees/`):

- **Worktree Boundary:** Write files **ONLY** within your designated worktree directory. Never alter the root repository files directly.
- **Port Clashes:** If ports `3000`, `3001`, or `4444` are blocked, clear them safely before launch:
  ```bash
  lsof -ti:3001,3000,4444 | xargs kill -9 2>/dev/null || true
  ```
- **Hot-Reload Gotcha:** The API server **does not auto-reload domain plugin changes**. When you edit domain files, kill the running server process and restart it.
- **Traffic Capture Requirement:** Connect an active browser instance for full capture; raw `curl` commands do not trigger transport classification.

---

## 7. Coding Standards & Conventions

### Language & Tooling
- **Language:** TypeScript 5.x with `strict: true`.
- **Linter & Formatter:** Biome (`biome.json`).
- **Test Framework:** Vitest with isolated mock environments.
- **Schema Validation:** Zod for all external inputs and network contracts.

### Naming & Organization
- **Files & Folders:** `kebab-case` (e.g., `session-manager.ts`, `transport-classifier.ts`).
- **Classes & Types:** `PascalCase` (e.g., `GenericSessionManager`, `TrafficEvent`).
- **Functions & Variables:** `camelCase` (e.g., `rateLimitedFetch`, `activeSession`).
- **Constants:** `UPPER_SNAKE_CASE` (e.g., `DEFAULT_TIMEOUT_MS`, `MAX_RETRIES`).
- **Imports:** Use monorepo aliases (`@interceptor/api`, `@interceptor/browser`, `@interceptor/shared`).

### API Communication Standards
- Use **relative URLs** (`/api/...`) for frontend-to-backend communication. Never hardcode `http://localhost:3001/...` in client code.
- Return standard HTTP status codes (`200`, `201`, `400`, `401`, `403`, `404`, `429`, `500`) with uniform JSON envelopes:
  ```typescript
  {
    "success": true,
    "data": { ... }
  }
  ```

---

## 8. Security & Secrets Management

- **Zero Committed Secrets:** Never commit `.env`, `.env.local`, API keys, session cookies, or private certificates.
- **Redaction Protocol:** Automatically mask credentials, Authorization tokens, and PII from log files and terminal outputs.
- **Safe Sandboxing:** Never execute untrusted code through `eval` or unsanitized shell spawning. Validate and sanitize all target URLs before passing them to browser automation.

---

## 9. Git & Commit Guidelines

- **Stage Selectively:** **Never** run `git add -A` or `git add .` indiscriminately. Stage only files related to your specific task by name (`git add path/to/file.ts`).
- **Conventional Commits:** Write clear, semantic commit messages:
  - `feat(domain): add automated GraphQL transport classifier`
  - `fix(browser): prevent memory leak during long-lived WebSocket sessions`
  - `refactor(shared): simplify session token expiration calculation`
  - `test(api): add integration test for domain proxy routes`
- **Pre-Commit Verification:** Run `./scripts/ci-local.sh` and verify all tests and lints pass with exit code `0` before committing.

---

## 10. Troubleshooting & Common Gotchas

| Issue | Root Cause | Solution |
| :--- | :--- | :--- |
| **Port 3001/3000 EADDRINUSE** | Zombie Node/Hono process holding port | Run `lsof -ti:3001,3000 \| xargs kill -9` |
| **Domain routes return 404** | Domain not registered in server index | Add plugin import to `register-domains.ts` and restart server |
| **Domain edits not reflecting** | Server lacks hot-module reload for domains | Stop server (`Ctrl+C` or `kill -9`) and restart via `pnpm dev` |
| **Missing traffic in `/browser/traffic`** | No active browser WebSocket client attached | Ensure browser instance is running and connected to `ws://localhost:3001/browser/stream` |
| **Lockfile conflicts** | Package versions mismatched across workspaces | Run `pnpm install --frozen-lockfile` or `pnpm dedupe` |
