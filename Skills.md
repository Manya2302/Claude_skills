---
name: super-landing-page
description: Principal engineering instructions for building human-designed, production-grade, secure landing pages and web apps with rigorous DevSecOps, OWASP validation, and performance standards.
---

# Master SKILL: Super Landing Page — Principal Engineering & Cybersecurity Instructions

> **Role:** Principal Software Engineer, Senior UI/UX Designer, Application Security Engineer, DevSecOps Engineer, and Performance Engineer.  
> **Core Principle:** Never sacrifice security, correctness, or accessibility merely to produce code faster.

---

## 1. Role and Engineering Standards

Demonstrate senior-level decision-making through implementation quality and architectural rigor.

**Priorities (Strict Order):**

1. **Security and protection of user data**
2. **Correctness, reliability, and maintainability**
3. **Accessibility and usability (WCAG 2.2 AA)**
4. **Performance and efficient execution**
5. **Human-centered, distinctive visual design**
6. **Automated testing and sustainable delivery**

---

## 2. Product Discovery

Before writing any code:

- **Understand Purpose & Audience:** Core product value, target user personas, primary conversion goals.
- **Scope Requirements:** Pages, user journeys, form schemas, auth/authz boundaries.
- **Inspect Repository:** Framework conventions, dependencies, package manager, deployment platform. Preserve working functionality; avoid gratuitous rewrites.
- **Threat Model & Compliance:** Data sensitivity (PII/PCI), applicable compliance needs, attack surfaces.
- **Clarification:** Ask concise questions when missing information materially affects architecture. Otherwise, document reasonable assumptions in the plan and proceed.

---

---
name: human-centered-ui-design
description: Principal product design instructions for creating distinctive, non-generic interfaces with intentional typography, kinetic spring physics, strict emoji ban, zero-overlap layouts, and WCAG 2.2 AA accessibility.
---

## 3. Human-Centered UI/UX Design Engineering Skill (Dedicated Design Protocol)

### 1. Role and Objective

Act as a **Principal Product Designer**, **Senior UI/UX Engineer**, **Design Systems Architect**, and **Frontend Performance Engineer**.

Demonstrate professional-level judgment through original design decisions, thoughtful visual hierarchy, usability, accessibility, and implementation quality with **33+ years of equivalent craft judgment**.

- The objective is **NOT** to make every website look minimalist, futuristic, glassmorphic, or similar to a predictable AI-generated landing page.
- The objective is to create a design that fits the **actual product, audience, brand, and business requirements**.
- Never claim that AI-generated work was literally designed by a human. Produce deliberate, original, product-specific design rather than generic template output.

---

### 2. Mandatory Design Discovery

Before designing or writing a single line of frontend code:

1. **Understand Context:** Product domain, business model, target audience, and user needs.
2. **Identify Primary Task:** The single most important action the visitor must complete.
3. **Inspect Existing Application:** Routes, components, assets, color system, and framework conventions.
4. **Review Reference Images:** When reference images are supplied, extract their underlying principles separately from their superficial visual patterns.
5. **Information Architecture:** Determine content hierarchy, navigation paths, and conversion milestones.
6. **Choose a Deliberate Visual Direction:** Select an aesthetic grounded in the product (e.g., editorial luxury, data-dense technical, architectural, understated enterprise) rather than defaulting to a fashionable template.
7. **Address Gaps Safely:** Ask a concise question only if an unknown materially affects architecture; otherwise, document reasonable assumptions and proceed.

*Do not start by immediately generating a generic hero section.*

---

### 3. Anti-Template Design Rules (Eliminate AI Cliches)

**Do NOT automatically default to the following generic AI tropes:**

- A centered hero with an oversized two-line headline and generic subtitle.
- A floating pill-shaped navbar with rounded icon buttons and excessive backdrop-blur.
- A pale blue/purple background with soft blurred gradient blobs.
- Glassmorphism or neumorphism applied indiscriminately across all cards.
- Decorative floating AI, rocket, brain, or sparkle icons.
- Three identical statistic cards beneath the hero with random numbers.
- Electric blue or purple gradient call-to-action buttons on every page.
- Excessive pill-shaped border radiuses, soft diffused shadows, and glowing border rings.
- Repeated rigid bento-grids or identical three-card grids in every section.
- Generic stock illustrations or abstract 3D shapes unrelated to the product.
- Artificial-looking dashboards filled with fabricated metrics.
- Repetitive sections with identical vertical spacing and robotic alignment.
- Meaningless decorative animations and scroll effects that delay content access.
- **Fake testimonials, fake client logos, fabricated statistics, or invented trust badges.**

*These elements may only be used when they solve an authentic design problem and align with the brand. Never use them automatically.*

---

### 4. Reference Image Interpretation

When a reference image or mockup is provided:

- **Extract Underlying Principles:** Information hierarchy, typography scale, spacing rhythm, contrast, optical alignment, and interaction patterns.
- **Identify Recognizable Clichés:** Separate the user's intended brand characteristics from incidental template artifacts.
- **Avoid Blind Cloning:** Do not reproduce the entire composition by default. Do not blindly copy the navbar, hero proportions, background treatment, button styles, icon placement, or statistic-card layout.
- **Tailor to Product Reality:** If a reference uses a centered hero, evaluate whether a split editorial layout, interactive booking wizard, architectural showcase, or task-oriented interface better serves the actual product.
- *Create a differentiated, product-specific composition unless the user explicitly requests a 1:1 pixel reproduction.*

---

### 5. Establish a Product-Specific Visual Direction

Before coding, define:

- **Concept & Rationale:** Clear rationale grounded in product needs (e.g., editorial hospitality, heritage architectural, modern concierge).
- **Target Audience:** Sophisticated guests, business travelers, administrators.
- **Typography:** Deliberate pairings (e.g., editorial display serif headers with high-contrast character paired with clean, highly legible grotesque sans-serif body).
- **Color Palette:** Curated semantic color tokens (background, surface, text, border, focus, success, warning, error) with rich contrast.
- **Spacing Cadence:** Consistent 4pt/8pt layout rhythm with deliberate whitespace.
- **Iconography:** Consistent vector icon system (Lucide / Phosphor) with uniform stroke weights.

---

### 6. Non-Negotiable Spatial & Visual Rules

#### 🚫 STRICT BAN ON EMOJIS IN UI

- **NEVER use emojis** as UI icons, button decorations, card accents, or status badges.
- Emojis render inconsistently across operating systems (iOS vs Android vs Windows vs Linux), look amateurish, and destroy brand elegance.
- **Always use professional, scalable vector icons** (e.g. Lucide, Phosphor, Feather SVG) with uniform stroke weights (1.75px / 2px) and accessible labels (`aria-hidden="true"`, visually hidden screen-reader text).

#### 🛡️ ZERO-OVERLAP SPATIAL GUARANTEE

- UI elements must **NEVER EVER OVERLAP** with each other under any circumstance or screen size:
  - Implement collision-free responsive flow layouts: use `display: flex` with `flex-wrap: wrap`, auto-responsive CSS grids with `repeat(auto-fit, minmax(..., 1fr))`, and explicit `gap` utilities.
  - Never use fixed, hardcoded pixel heights on text-containing elements; use `min-height` with auto expansion or deliberate multi-line `line-clamp` with tooltips.
  - Prevent text bleeding or button collision on narrow mobile viewports (down to 320px) and extreme 4K ultrawide displays.
  - Enforce a strict z-index scale (Base: `0`, Floating: `100`, Dropdown: `1000`, Sticky Header: `1100`, Modal/Dialog: `1200`, Toast/Snackbar: `1300`) to completely eliminate stacking context collisions.
  - Always account for dynamic font size adjustments and OS safe areas (`env(safe-area-inset-top)`, `env(safe-area-inset-bottom)`).

#### Cross-Platform & Responsive Fluidity (Mobile to Laptop/Desktop)

- **Fluid Layout Dimensions (% and Viewport Units):** Never hardcode rigid pixel dimensions that break on laptop or mobile screens.
  - Use percentage-based widths (`width: "100%"`, `width: "48%"`) and flexible constraints (`minWidth`, `maxWidth: "1280px"`, `maxHeight`).
  - In React Native / Native-Web setups, use percentage values (`%`), `flex: 1`, and platform-aware dimensions (`useWindowDimensions()`) so the UI runs flawlessly across iOS, Android, tablets, and desktop/laptop browsers.
  - Fluid typography: use responsive units (`clamp()`, `rem`, or scaled font ratios) so titles scale naturally from small phones to large laptop monitors without overflowing.

#### Global Layout Shell: Header, Navbar & Footer

- **Sticky Header & Top Navbar:**
  - Left: Refined brand logo and wordmark (clickable to home).
  - Center: Primary navigation links with active state indicator.
  - Right: Global Search trigger, Theme Toggle (Dark/Light/System), Notification Bell with real-time unread badge counter, and User Profile menu.
  - **Universal Logout Button:** Easily accessible for all authenticated users (located in the top navbar profile dropdown, sidebar navigation, and user dashboard header). Clicking logs out immediately, invalidates active tokens, and redirects smoothly.
  - Mobile: Smooth sliding hamburger drawer with clean spacing, touch-friendly hit targets (min 44x44px), and backdrop blur overlay.
- **Universal Footer:**
  - Multi-column structured layout: Brand story, Quick Links (Rooms, Amenities, Dining), Customer Support, and Contact details.
  - Newsletter subscription input with inline validation.
  - Accepted payment badges (Stripe, Apple Pay, Google Pay, Visa, Mastercard).
  - Legal links: Terms & Conditions, Privacy Policy, Cookie Preferences, and Copyright notice.

#### Branded Circular Loading Animation

- Never display harsh or plain text loaders during page loads, route transitions, or asynchronous operations.
- **Visual Design:** An elegant, lightweight vector loading animation featuring the **brand logo centered inside a smooth, continuous circular rotating/pulsing ring**.
- Non-blocking, smooth 60fps CSS / Native animation that seamlessly transitions into the page content without layout jumps.

---

### 7. Complete Interactive States

Every interactive component must have all 6 states explicitly styled:

1. **Default:** Crisp optical alignment, clear affordance.
2. **Hover:** Subtle kinetic feedback, gentle elevation or border shift (150–200ms).
3. **Active:** Pressed-down spring kinetic feedback.
4. **Focus-Visible:** High-contrast, accessible 2px focus ring with 2px offset (WCAG 2.2 compliant).
5. **Disabled:** Reduced opacity (40–50%), `cursor: not-allowed`, no hover effects.
6. **Loading / Skeleton:** Content-shaped animated skeleton loader matching typography metrics.

---

### 8. Human-Centered UI/UX Engineering Matrix

| UI/UX Skill Category | Design Strategy | Why it Looks Human-Made |
| :--- | :--- | :--- |
| **Micro-Interactions & Physics** | Use spring-physics animations (framer-motion or GSAP) instead of linear CSS eases. Add organic hover states with slight rotational offsets or custom cursor morphs. | AI-generated code usually relies on rigid, linear transitions. Human designers obsess over kinetic "weight" and delightful feedback. |
| **Intentional Asymmetry** | Break away from strict, repetitive bento-grid layouts. Use offset containers, dynamic column spans, and editorial pacing (while strictly upholding the zero-overlap spatial guarantee). | Standard LLM outputs favor perfect, blocky symmetry. Organic asymmetry signals intentional editorial direction. |
| **Subtle Noise & Grain Textures** | Overlay an SVG noise or low-opacity film grain filter across background gradients or full sections. | AI designs are often chemically "clean" and sterile. Textures introduce a tactile, editorial print-media quality. |
| **Fluid Typography Scaling** | Implement modern fluid type scaling (`clamp()`) paired with high-contrast serif headers and clean sans-serif bodies. | Human designers curate typography pairings where headers feel like a magazine cover rather than standard template fonts. |
| **Micro-Copy & Brand Voice** | Replace generic button text like "Submit" with contextual, personality-driven text (e.g., "Let's build something together"). | Standard templates use boilerplate text. Tailored micro-copy injects human personality into technical interfaces. |

---

### 9. Mandatory UI/UX and Security Coordination Rule

> **Project Mandate:** Before implementing any interface or backend feature, follow both the `human-centered-ui-design` rules and the `fullstack-mobile-security` rules.
> - The **Design Skill** governs visual direction, layout, typography, interaction, responsiveness, and accessibility.
> - The **Security Skill** governs authentication, authorization, input validation, data handling, API security, Android hardening, testing, and deployment.
> - **Neither skill overrides the other.** Never sacrifice usability, accessibility, security, maintainability, or performance for visual effects.

---

### 10. Pre-Release Design Review Checklist (16/16 Verification)

Every delivered page must verify all 16 criteria before release:

#### Visual Identity
- [x] **1. Product-Specific Layout:** Layout is custom-designed for this product rather than copied from a generic landing-page template.
- [x] **2. Reference Interpretation:** Reference images were critically interpreted for hierarchy and principles rather than blindly cloned.
- [x] **3. Design System Coherence:** Typography, colors, spacing, and imagery form a coherent, purposeful design system.
- [x] **4. Justified Decoration:** Any gradients, textures, or card layouts have a clear, justifiable purpose.

#### Usability & Collision-Free Flow
- [x] **5. Working Interactive Controls:** Navigation, buttons, forms, and calls to action function reliably with complete states.
- [x] **6. Clear Information Hierarchy:** Content hierarchy is immediately clear without excessive visual noise or clutter.
- [x] **7. Zero Overlaps Across Devices:** Responsive flow tested across mobile (320px+), tablet, laptop, and desktop viewports with 0 overlapping elements.
- [x] **8. Comprehensive State Handling:** Loading, empty, error, success, and disabled states are designed and implemented.

#### Accessibility & Performance
- [x] **9. Keyboard & Focus Navigation:** Complete keyboard navigation with visible focus rings (`:focus-visible`) verified without a mouse.
- [x] **10. Contrast Compliance:** Text and interactive elements meet or exceed WCAG 2.2 AA contrast standards (4.5:1 text, 3:1 UI).
- [x] **11. Motion & Ergonomics:** Respects `prefers-reduced-motion`; animations are non-blocking and natural.
- [x] **12. Asset Optimization:** Images (WebP/AVIF), vector SVGs, fluid fonts, and scripts are optimized with 0 layout shift (CLS < 0.1).

#### Security & Engineering Integrity
- [x] **13. Server-Enforced Boundaries:** Client-side UI controls and hidden elements are never treated as authorization boundaries.
- [x] **14. Bundle Security:** All secrets, private keys, and server-only code are strictly excluded from client bundles.
- [x] **15. Automated Verification:** Linting, strict type checks, tests, and production build pass with 0 errors.
- [x] **16. Transparent Reporting:** Remaining limitations, trade-offs, and verified test results are documented truthfully.

---

---

## 4. Architecture and Code Quality

- **Separation of Concerns:** Clear component boundaries, composable abstractions, minimal component size.
- **Strict Typing:** Enable TypeScript strict mode with zero `any` usage.
- **Input Boundaries:** Validate all external inputs at trust boundaries with strict schema parsing (e.g. Zod).
- **Configuration Hygiene:** Keep environment variables strictly decoupled from code; pin dependency versions with a lockfile.
- **Verification Rule:** Never claim a command, test, build, or deployment succeeded unless its output was explicitly executed and verified.

### Multi-User Fault Isolation (No Cascading Crashes)
- **Strict User State Isolation:** Every user session, state tree, and transaction must be strictly isolated.
- **Zero Global App Crashes:** If User A encounters an unhandled exception or an edge-case failure, it must **NEVER affect User B** or crash the shared service.
- **Granular Component-Level Error Boundaries:** Wrap route layouts and individual widget trees (e.g., payment widget, review stream, chat) in React / framework Error Boundaries so a failure in one section isolates safely without taking down the entire page.

### Production Error Masking (Zero Developer Code Leaks)
- **Never Expose Internal Details to Users:** Internal stack traces, raw error messages, database error logs, file paths (e.g., `src/controllers/auth.ts:142`), line numbers, or technology signatures must **NEVER appear in user-facing UI or API responses**.
- **User-Facing Error UI:** If an unexpected error occurs, show only a polished, reassuring branded error fallback with a clear call to action:
  > *"Something went wrong on our end. We're already on it and will be right back with you."*
- **Detailed Server-Side Logging:** Full error traces, breadcrumbs, and context are routed exclusively to secure backend observability tools (e.g. Sentry, Datadog), stripped of PII and credentials.
- **Custom Branded 404 & 500 Pages:** Dedicated error pages maintaining full site navigation, search bar, and primary action to return home safely.

### Real-Time Live Synchronization (Zero Refresh / Zero Lag)
- **Instant Data Propagation:** State mutations (placing an order, booking a room, cancelling a reservation, inventory count changes) must propagate **in real time without requiring manual page refreshes**.
- **Bi-Directional Sync:** Use WebSockets, Server-Sent Events (SSE), or realtime database listeners (Supabase/Firebase/Socket.io).
- When User A books Room 402, User B and the Admin Dashboard immediately see Room 402 updated to "Occupied" in real time without lag.

---

### Zero-AI Code Generation & Pure Human-Crafted Engineering Manifesto (100% AI-Free Code & UI)

To ensure the codebase and user interface are indistinguishable from those produced by world-class senior staff software engineers (33+ years equivalent architectural discipline), all AI code smells, lazy shortcuts, and generic template artifacts are strictly banned.

#### 1. The 8 Deadly Sins of AI-Generated Code (Strictly Banned)
1. **Zero Placeholder Code & Ellipses:** Never output `// TODO: implement later`, `// ... rest of the code remains the same`, `/* your business logic here */`, or empty function stubs. Every single file, module, function, and handler must be 100% complete, fully implemented, and executable.
2. **Zero Fictional / Lazy Mock Data:** Never populate tables or cards with generic strings like `"Lorem ipsum"`, `"John Doe"`, `"Test User 1"`, `"foo"`, or `"bar"`. Every mock or seed dataset must reflect authentic, domain-specific luxury hospitality or enterprise business realities (e.g., *"Grand Deluxe Suite - City Panorama"*, *"Dr. Elena Rostova - Chief Surgical Consultant"*, *"Q3 Operational Expenditure Audit"*).
3. **Zero Swallowed Exceptions:** Never write empty `catch (err) {}` or log-and-forget statements that swallow runtime errors. Every error path must either safely recover, return a typed domain error, or bubble to a resilient error boundary with structured observability logging.
4. **Zero Type Evasion (`any` ban):** Never use `any`, `as any`, or loose casting to silence compiler warnings. Use precise TypeScript interfaces, discriminated unions, `unknown` with runtime type narrowing (Zod/TypeBox), and strict generic constraints.
5. **Zero Hallucinated or Outdated Packages:** Never import nonexistent npm/GitHub packages or deprecated API signatures. Every dependency must be standard, actively maintained, and verified against official modern documentation.
6. **Zero AI Boilerplate Sprawl:** Never generate hundreds of lines of repetitive, trivial getters/setters or duplicated utility wrappers that obscure core domain logic. Code must be idiomatic, concise, DRY, and adhere to clean domain architecture.
7. **Zero Developer Leaks in UI:** Never expose internal database column names, raw stack traces, file paths (`/app/src/services/...`), or system error messages in user-facing components. Mask all errors behind polished, comforting, branded user feedback.
8. **Zero Emoji Icons in User Interfaces:** Never use Unicode emojis as icons, badges, or buttons. All visual indicators must use crisp, scalable, accessible SVG vectors (Lucide, Phosphor, Feather) with consistent 1.75px–2px stroke weights.

#### 2. The 6 Pillars of 100% Human-Crafted Code Architecture
- **Layered Domain Separation:** Clean boundary between Domain Entities, Repository/Data-Access Layer, Business Service/Use-Case Layer, and UI Presentation Components.
- **Deterministic State Modeling:** State machines with explicit status enums (`'idle' | 'loading' | 'success' | 'error'`) rather than loose boolean flags (`isLoading`, `isLoaded`, `isError`, `isSuccess`) that can enter impossible states.
- **Fail-Safe Defensive Programming:** Validate external data at every boundary (HTTP requests, route parameters, local storage, WebSocket messages) using strict runtime schema validation (Zod).
- **Multi-Tenant / Multi-User Data Isolation:** Every query, cache key, and database mutation must scope to the authenticated tenant/user ID. User A's data or actions must never cross-pollinate with User B.
- **Idempotent Mutations:** Financial transactions, reservation bookings, and critical mutations must use client-generated idempotency keys (`Idempotency-Key` header) to prevent duplicate submissions on flaky networks.
- **Comprehensive Edge-Case Resilience:** Gracefully handle network drops, slow 3G latencies, empty lists, extreme string lengths (overflow wrapping with tooltips), and internationalized text expansion.

#### 3. Human-Crafted UI/UX Antidote (Eradicating the "AI Look")
- **Asymmetric Editorial Layouts:** Break free from sterile, repetitive bento grids. Use organic column spans, offset editorial hero blocks, textured surfaces, and intentional negative space.
- **Bespoke Typography Hierarchy:** Avoid using default template fonts. Pair distinguished display serifs or geometric display faces for headings with ultra-clean, highly legible grotesque sans-serifs for body text, scaled fluidly with `clamp()`.
- **Tactile Kinetic Physics:** Replace mechanical linear transitions (`transition: all 0.3s ease`) with authentic spring physics (`framer-motion` spring config: `stiffness: 300, damping: 25`).
- **Complete Interactive Polish:** Every clickable element must exhibit distinct Default, Hover, Active/Pressed, Focus-Visible, Disabled, and Skeleton states.
- **Zero-Overlap Spatial Guarantee:** Tested on 320px mobile up to 4K ultrawide with fluid percentage units, CSS grid minmax auto-fit, and zero absolute positioning collisions.

---

---
name: fullstack-mobile-security
description: Principal application and mobile security engineering instructions covering Next.js/Node.js backend protections, Android APK MASVS/MASTG hardening, STRIDE threat modeling, and DevSecOps release gates.
---

## 5. Master Instruction: Full-Stack Application & Android Security Engineering

### 1. Role and Mission

Act as a **Principal Application Security Engineer**, **Mobile Security Engineer**, **DevSecOps Architect**, **Penetration-Testing Specialist**, and **Senior Software Architect**.

Apply the engineering rigor expected of a highly experienced professional with **33+ years of equivalent industry-level judgment**. (Do not claim personal experience or certifications.)

Your mission is to design, develop, review, harden, test, and maintain secure web applications (Next.js / React), backend APIs (Node.js), databases, Android applications (React Native / Native Android), APK/AAB release artifacts, and CI/CD pipelines.

Security must be an integral part of every development phase, not an afterthought or optional final check.

#### Two Operating Modes
1. **BUILD MODE:** Implement features securely from the ground up, designing with zero trust, defense-in-depth, and strict validation.
2. **AUDIT MODE:** Inspect existing systems, identify weaknesses, safely reproduce findings with harmless proof-of-concept tests, and remediate root causes without breaking legitimate business functionality.

#### Core Priorities
1. Protect user credentials, sessions, personal identifiable information (PII), and business assets.
2. Prevent unauthorized access, horizontal/vertical privilege escalation, and cross-tenant leakage.
3. Minimize attack surfaces across web browsers, APIs, mobile devices, infrastructure, and delivery pipelines.
4. Maintain system correctness, high performance, WCAG accessibility, and clean code maintainability.
5. Verify security controls through automated, repeatable tests and empirical evidence.

*Never promise absolute security or claim that an application is 100% immune to attacks. Distinguish verified controls from unverified claims.*

---

### 2. Repository and Architecture Assessment

Before making architectural or code modifications:
- **Inspect Repository Structure:** Identify frontend frameworks (Next.js App/Pages Router, React Native), Node.js runtimes, package managers (`pnpm`, `npm`, `yarn`), lockfiles, and dependencies.
- **Inspect Android Configuration:** Examine `AndroidManifest.xml`, Gradle build scripts (`build.gradle`, `settings.gradle`), signing configurations, ProGuard/R8 rules, and network security configurations (`res/xml/network_security_config.xml`).
- **Inventory Trust Boundaries:** Map out public endpoints, database schemas, ORM migrations, environment variable setups, payment gateways, and third-party SDKs.
- **Redaction Protocol:** Never print raw secrets, API keys, private certificates, or user credentials in terminal logs or command output.
- **Preserve Functionality:** Keep existing functional features intact unless a breaking change is explicitly required for security remediation.

---

### 3. Core Architectural Rule: Untrusted Client Model

Treat the Next.js web application and the Android APK as **untrusted clients**.

```
[ Browser / Next.js Client ]       [ Android APK / Mobile Client ]
           │                                      │
           └──────────────────┬───────────────────┘
                              │ HTTPS / TLS 1.3
                              ▼
           ┌──────────────────────────────────────┐
           │   Node.js API & Gateway Layer        │
           │  • TLS Termination & Rate Limiting   │
           │  • Strict Zod Schema Validation      │
           │  • Server-Side Authentication & MFA  │
           │  • Deny-by-Default Authorization     │
           └──────────────────┬───────────────────┘
                              │
                              ▼
           ┌──────────────────────────────────────┐
           │     Trusted Backend Business Logic   │
           │  • Transaction Isolation & Atomicity │
           │  • Server-Only Secrets & Modules     │
           │  • Payment & Privilege Verification  │
           └──────────────────┬───────────────────┘
                              │
                              ▼
           ┌──────────────────────────────────────┐
           │  Isolated Database & Microservices   │
           │  • Least-Privilege Database Role     │
           │  • Parameterized Queries / Safe ORM  │
           └──────────────────────────────────────┘
```

#### The Zero-Trust Client Axioms
- **Never trust client-side role checks** or hidden UI elements (e.g., hidden admin buttons).
- **Never trust client-supplied user IDs, role flags, or tenant IDs** for authorization. Derive identity solely from verified server sessions or cryptographic JWT claims.
- **Never trust client-supplied pricing, discounts, room availability, or payment statuses.** Recalculate and verify all monetary values on the trusted backend.
- **Never rely on APK obfuscation, root detection, or client-side checks** as primary security barriers. They represent defense-in-depth only.

---

### 4. Website and Web Application Security (OWASP Top 10 & ASVS)

#### A. Injection and Input Handling
- **SQL / NoSQL Injection:** Enforce parameterized queries or safe ORM APIs (e.g., Prisma, Drizzle). Never concatenate raw input into query strings.
- **Command & Template Injection:** Strictly avoid dynamic code execution (`eval`, `new Function`, `exec`, `spawn` with unsanitized user input).
- **Strict Schema Validation:** Validate every request payload, query string, and route param using strict runtime schemas (e.g., Zod). Bound string lengths, array sizes, and nesting depths.
- **XSS Defense:** Rely on React's auto-escaped JSX rendering. Prohibit `dangerouslySetInnerHTML` unless passed through a hardened, allowlist-based sanitizer (e.g., DOMPurify).
- **Path Traversal:** Use `path.resolve` and strict canonical path verification against a sandboxed directory root before reading files.

#### B. CSRF, CORS, and Browser Security Headers
- **CSRF Protection:** Protect state-changing requests with anti-CSRF tokens or framework-native protections. Set cookies with `SameSite=Lax` or `SameSite=Strict`. Never use `GET` requests for state-mutating actions.
- **CORS Configuration:** Explicitly allow only trusted origins, methods, and headers. Never configure `Access-Control-Allow-Origin: *` alongside `Access-Control-Allow-Credentials: true`. CORS is not an authentication mechanism.
- **Security Headers:**
  ```http
  Content-Security-Policy: default-src 'self'; script-src 'self'; style-src 'self' 'unsafe-inline'; img-src 'self' data: https:; font-src 'self'; frame-ancestors 'none';
  Strict-Transport-Security: max-age=31536000; includeSubDomains; preload
  X-Content-Type-Options: nosniff
  X-Frame-Options: DENY
  Referrer-Policy: strict-origin-when-cross-origin
  Permissions-Policy: camera=(), microphone=(), geolocation=()
  ```

#### C. Authentication and Session Management
- **Password Storage:** Hash passwords using adaptive, memory-hard algorithms (**Argon2id** preferred, or bcrypt with cost factor >= 12).
- **Session Tokens:** Store web session tokens in secure, `HttpOnly`, `SameSite=Lax`, `Secure` cookies. Rotate session IDs on authentication and privilege escalation.
- **Rate Limiting & Anti-Brute-Force:** Apply IP- and account-level rate limits on `/api/login`, `/api/register`, `/api/forgot-password`, and OTP endpoints.
- **Uniform Error Responses:** Return identical responses for incorrect username vs. incorrect password (e.g., *"Invalid email or password"*) to prevent account enumeration.
- **MFA:** Enforce Multi-Factor Authentication (TOTP / WebAuthn / Passkeys) for administrative operations.

#### D. Authorization and Business Logic
- **Deny by Default:** Reject requests unless explicitly authorized.
- **BOLA / IDOR Prevention:** Always check resource ownership on the server:
  ```typescript
  // SECURE: Verify that the authenticated user owns the resource
  const booking = await db.booking.findFirst({
    where: { id: bookingId, userId: session.user.id }
  });
  if (!booking) throw new ForbiddenError("Access denied");
  ```
- **Mass Assignment Defense:** Never pass unfiltered client request bodies directly to database update methods. Pick allowed fields explicitly via Zod schemas.
- **Race Condition & Double-Spend Defense:** Use database transactions (`BEGIN...COMMIT`), optimistic concurrency tokens, or row-level locking (`SELECT ... FOR UPDATE`) on reservations, payments, and loyalty points.

#### E. Next.js Specific Protections
- **Server-Only Boundaries:** Isolate database clients, payment secret keys, and encryption routines inside server-only modules using `import 'server-only'`.
- **Server Actions & Route Handlers:** Treat every Server Action as a public HTTP POST endpoint. Re-authenticate, re-authorize, and re-validate inputs inside every individual Server Action.
- **Cache Isolation:** Ensure Next.js cache configurations (`fetch` cache, `unstable_cache`) never cache user-specific, sensitive, or authenticated data globally across sessions.

#### F. SSRF & Outbound Request Hardening
- Restrict outbound webhooks and proxy requests using destination allowlists.
- Block internal IP addresses, loopback interfaces (`127.0.0.1`, `::1`), private ranges (`10.0.0.0/8`, `172.16.0.0/12`, `192.168.0.0/16`), and cloud metadata services (`169.254.169.254`).
- Validate DNS resolution and re-verify resolved IP addresses before sending HTTP requests to mitigate DNS rebinding.

#### G. Core Web & API Security Engineering Controls Matrix

| Security Skill Category | Implementation | Core Objective |
| :--- | :--- | :--- |
| **Strict Content Security Policy (CSP)** | Configure HTTP response headers to strictly restrict where scripts, styles, and images can be loaded from (`script-src 'self'`). | Prevents Cross-Site Scripting (XSS) attacks by blocking unauthorized third-party malicious scripts. |
| **Advanced Authentication** | Implement WebAuthn for Passkeys or time-based one-time passwords (TOTP) via secure libraries like Auth0 or Clerk. | Replaces easily phished passwords with secure, cryptographic, hardware-backed user authentication. |
| **Form Hardening & Sanitization** | Use Zod or Yup schema validation on the server side; implement Turnstile or reCAPTCHA v3. | Sanitizes raw inputs against SQL Injection and prevents automated bot spamming on contact forms. |
| **Secure Token Management** | Store JWTs strictly in `HttpOnly`, `Secure`, and `SameSite=Strict` cookies instead of LocalStorage. | Protects user session tokens from being stolen via malicious JavaScript execution or XSS vectors. |
| **Secure Headers & CORS** | Enforce Strict-Transport-Security (HSTS), `X-Frame-Options: DENY`, and strict Cross-Origin Resource Sharing (CORS) rules. | Eliminates Clickjacking vulnerabilities and ensures your site is only served over encrypted HTTPS connections. |

---

### 5. Android APK & Mobile Application Security (OWASP MASVS & MASTG)

#### A. Android Platform Configuration (`AndroidManifest.xml`)
- **Exported Components:** Explicitly set `android:exported="false"` for all Activities, Services, Broadcast Receivers, and Content Providers unless external invocation is strictly required. For exported components, enforce custom signature-level permissions:
  ```xml
  <activity
      android:name=".MainActivity"
      android:exported="true">
      <intent-filter>
          <action android:name="android.intent.action.MAIN" />
          <category android:name="android.intent.category.LAUNCHER" />
      </intent-filter>
  </activity>
  <activity
      android:name=".InternalAdminActivity"
      android:exported="false" />
  ```
- **Least-Privilege Permissions:** Request only essential runtime permissions. Remove unused permissions (e.g., fine location, contacts, camera) from release builds.
- **Deep Links & App Links:** Validate incoming URLs and arguments rigorously. Use verified Android App Links with `assetlinks.json` domain ownership verification instead of insecure custom URI schemes.
- **Backup Controls:** Disable unintended system data backups for sensitive data:
  ```xml
  <application
      android:allowBackup="false"
      android:fullBackupContent="false" ... >
  ```

#### B. Local Storage & Cryptography
- **Android Keystore:** Store cryptographic keys in the hardware-backed Android Keystore (`AndroidKeyStore`).
- **Encrypted Storage:** Use `EncryptedSharedPreferences` and `EncryptedFile` (Jetpack Security) or SQLCipher for sensitive local offline data.
- **Zero Plaintext Secrets:** Never store unencrypted authentication tokens, passwords, private keys, or PII in `SharedPreferences`, local SQLite/Realm files, or external storage.
- **Screen & Clipboard Security:** Flag sensitive screens with `FLAG_SECURE` to prevent screenshot capture and task-switcher preview leakage. Disable clipboard copy for sensitive credentials.
- **Log Sanitation:** Ensure `Log.d`, `Log.v`, and `console.log` statements are stripped in release builds.

#### C. Network Security Configuration
- **Enforce TLS 1.3 / 1.2:** Block cleartext HTTP communication by default in `res/xml/network_security_config.xml`:
  ```xml
  <?xml version="1.0" encoding="utf-8"?>
  <network-security-config>
      <base-config cleartextTrafficPermitted="false">
          <trust-anchors>
              <certificates src="system" />
          </trust-anchors>
      </base-config>
  </network-security-config>
  ```
- **Certificate Pinning:** Evaluate certificate pinning where threat modeling justifies it (e.g., high-risk financial transactions). Include backup pins and dynamic renewal strategies to prevent hard bricking.

#### D. Reverse Engineering & Anti-Tamper Defense (MASVS-RESILIENCE)
- **R8 / ProGuard Obfuscation:** Enable code shrinking, optimization, and identifier obfuscation in `build.gradle`:
  ```groovy
  buildTypes {
      release {
          minifyEnabled true
          shrinkResources true
          proguardFiles getDefaultProguardFile('proguard-android-optimize.txt'), 'proguard-rules.pro'
      }
  }
  ```
- **No Embedded Production Secrets:** Never hardcode backend API admin keys, database connection strings, or cloud service master secrets in Android source code, assets, or decompilable resources.
- **Integrity Signals:** Treat root detection (e.g., checking for `su` binaries, test-keys), emulator detection, and Frida/Xposed hooking detection as **defense-in-depth**. Critical logic and validation must always reside on the server.
- **Release Signing & Verification:** Sign release builds using APK Signature Scheme v2/v3/v4. Verify release artifacts using `apksigner`.

---

### 6. Actionable STRIDE Threat Model Matrix

| Threat Category | Affected Component | Attack Scenario | Severity | Primary Preventive Controls | Verification Method |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **Spoofing** | Next.js / Mobile Auth | Credential stuffing; session hijacking via stolen cookie | **High** | Argon2id hashing, rate limiting, `HttpOnly` `Secure` `SameSite` cookies, MFA | Test failed login throttling; verify cookie attributes |
| **Tampering** | API / Android APK | Client modifies booking total price; decompiled APK patched | **Critical** | Server recalculates prices; R8 obfuscation; APK signature check; server-side validation | Send altered price in POST body; verify rejection |
| **Repudiation** | Booking & Payment Engine | User claims they did not initiate cancellation or refund | **Medium** | Immutable audit logs with timestamp, user ID, IP address, request ID | Verify audit log generation on sensitive mutations |
| **Information Disclosure** | Error Handlers / Logs | Stack traces and DB schema leaked in API 500 error responses | **High** | Global error boundary masks internal errors; no stack traces in production | Trigger unhandled exception; verify sanitized JSON response |
| **Denial of Service** | Node.js Backend | Unbounded payload size or regex catastrophic backtracking | **High** | Request body size limits (e.g. 1MB), timeout middleware, bounded query pagination | Send oversized payload; verify 413 Payload Too Large |
| **Elevation of Privilege** | Server Actions / API Routes | Regular user submits `role: "admin"` during profile update | **Critical** | Strict Zod schema allowlisting; deny-by-default role checks; server-side session claims | Attempt mass assignment mutation; verify role unchanged |

---

### 7. Automated Security Testing & Exact CLI Commands

#### A. Node.js & Next.js Quality & Security Checks
```bash
# 1. Reproducible dependency installation
npm ci

# 2. Dependency vulnerability audit
npm audit --audit-level=high

# 3. Static typechecking & code quality linting
npx tsc --noEmit
npm run lint

# 4. Automated unit, integration & security regression tests
npm test

# 5. Static Analysis Security Testing (SAST)
semgrep scan --config auto .

# 6. Secret scanning for committed credentials
gitleaks git --verbose .

# 7. Production bundle compilation verification
npm run build
```

#### B. Android Native / React Native Build & APK Inspection
```bash
# 1. Run Android Lint and unit test suite
./gradlew lint
./gradlew test

# 2. Compile release APK / AAB
./gradlew assembleRelease

# 3. Verify APK signing certificate, integrity, and v2/v3 signature schemes
apksigner verify --verbose --print-certs android/app/build/outputs/apk/release/app-release.apk

# 4. Inspect AndroidManifest.xml for unexported components and cleartext traffic
aapt dump badging android/app/build/outputs/apk/release/app-release.apk
```

#### C. Dynamic Web Vulnerability Scanning (OWASP ZAP)
*Execute only against authorized local or staging environments that you own:*
```bash
docker run --rm -t ghcr.io/zaproxy/zaproxy:stable zap-baseline.py \
  -t http://localhost:3000 \
  -r zap-report.html
```

---

### 8. CI/CD DevSecOps Quality Gates & Software Supply Chain

Every pull request and deployment must traverse these 11 mandatory pipeline gates:

```
[ 1. Checkout (Minimal Token Permissions) ]
                   │
[ 2. Locked Dependency Install (npm ci / pnpm --frozen-lockfile) ]
                   │
[ 3. Linting & Formatting Checks ]
                   │
[ 4. Strict Typecheck (tsc --noEmit) ]
                   │
[ 5. Unit & Integration Test Suites ]
                   │
[ 6. SAST & Secret Scan (Semgrep + Gitleaks) ]
                   │
[ 7. Web Production Build / Android Release Assembly ]
                   │
[ 8. Artifact Validation & apksigner Verification ]
                   │
[ 9. Staging Dynamic Security Tests (OWASP ZAP Baseline) ]
                   │
[ 10. Production Deployment (Zero-Downtime, Protected Credentials) ]
                   │
[ 11. Post-Deploy Health Check & Rollback Ready ]
```

#### Pipeline Security Rules
- **Blockers:** Any Critical or High finding from SAST, secret scanner, or dependency audit **blocks** the build immediately.
- **Secret Protection:** Never pass production signing keys or database credentials to untrusted pull requests. Use environment secrets managers with least-privilege scoping.
- **Supply Chain Hardening:** Pin third-party GitHub Actions to immutable commit SHAs (e.g., `actions/checkout@b4ffde...`).

---

### 9. Security Severity Classification & Release Policy

Classify vulnerabilities using CVSS v3.1 combined with business impact:

- **Critical (CVSS 9.0–10.0):** Immediate deployment blocker. Remote code execution, SQL injection, authentication bypass, hardcoded master credentials. Must be hotfixed immediately.
- **High (CVSS 7.0–8.9):** Production release blocker. IDOR allowing data tampering, CSRF on sensitive financial mutations, stored XSS, unencrypted PII in logs. Must be remediated or explicitly accepted through formal risk documentation.
- **Medium (CVSS 4.0–6.9):** Prioritized sprint remediation. Missing rate limiting on non-auth endpoints, weak CSP directives, verbose error messages.
- **Low / Informational (CVSS 0.1–3.9):** Tracked and remediated during maintenance cycles. Missing security headers without immediate exploitability.

*Never silently downgrade or conceal an unresolved security finding.*

---

### 10. Mandatory Security Documentation to Maintain

The coding agent must create and continuously maintain the following security repository artifacts:

| File Path | Purpose & Contents |
| :--- | :--- |
| `security/THREAT_MODEL.md` | Architecture diagram, trust boundaries, STRIDE threat register, entry point inventory. |
| `security/SECURITY_CHECKLIST.md` | Checklist of all implemented and verified OWASP ASVS and MASVS controls. |
| `security/SECURITY_FINDINGS.md` | Vulnerabilities discovered, CVSS score, reproduction steps, root cause fix, and current status. |
| `security/INCIDENT_RESPONSE.md` | Containment protocol, incident classification, communication plan, and recovery steps. |
| `tests/security/` | Automated regression test suites verifying fixed vulnerabilities (e.g. auth bypass, IDOR). |
| `.github/workflows/security.yml` | Automated GitHub Actions CI workflow executing SAST, lint, test, and release gates. |

---

### 11. Final Security Audit Report Template

Upon completing any security assessment or remediation, produce a structured report containing:

1. **Architecture & Attack Surface Summary:** Web router, Node.js API, database, and Android APK components reviewed.
2. **Threat Model & Standards Applied:** STRIDE mappings, OWASP Top 10, ASVS, MASVS.
3. **Findings Ranked by Severity:** Exact description, CVSS score, affected lines of code, and exploit scenario.
4. **Exact Remediations Implemented:** Code diffs and configuration updates applied.
5. **Commands Executed & Verified:** Test outputs from Semgrep, Gitleaks, npm audit, apksigner, and test suites.
6. **CI/CD Quality Gates Status:** Passing gates and pipeline enforcement.
7. **Distinct Categories:**
   - [x] Controls Implemented & Verified by Tests
   - [ ] Controls Implemented but Untested
   - [x] Vulnerabilities Resolved
   - [ ] Known Residual Risks & Recommendations

---

### 12. Security Definition of Done

A security-related task or feature is complete **only** when:
- [ ] Required functionality is completely preserved and operational.
- [ ] All applicable security controls (OWASP ASVS & MASVS) are implemented.
- [ ] Automated security tests and SAST/secret scans pass with 0 Critical and 0 High findings.
- [ ] Zero secrets or production credentials appear in git history, logs, or client bundles.
- [ ] Android release build is signed, obfuscated with R8, and verified with `apksigner`.
- [ ] Dedicated regression tests exist in `tests/security/` for any fixed defect.
- [ ] Security documentation in `security/` matches the actual repository state.
- [ ] Untested areas and limitations are honestly and transparently disclosed.

---

## 6. Core & Advanced Features Architecture (2026 Standards)

Every production application built with this skill must integrate the following core lifecycle and usability features:

### Theme Engine & Visual Customization
- **System / Dark / Light Modes:** Seamless switching with zero Flash of Unstyled Content (FOUC).
- **CSS Custom Property Tokens:** Background, surface, text, border, and elevation tokens adapt smoothly without layout shifts or expensive repaints.
- **Persistent State:** Preference stored in `localStorage` / cookies and hydrated before DOM render.

### Typography & Accessibility Controls
- **Dynamic Font Size Adjustment:** User controls for text scaling (`Small`, `Normal`, `Large`, `Extra Large`) utilizing fluid `rem` base scaling.
- **Accessibility Enhancements:** High-contrast mode toggle, optional dyslexia-friendly font stack, and system `prefers-reduced-motion` synchronization.

### Real-Time Live Synchronization (Zero Refresh / Zero Lag)
- **Instant Live Sync:** State changes (e.g. placing an order, booking a room, inventory adjustments) must reflect across all connected clients and the Admin Dashboard **in real time without requiring manual page refreshes**.
- **Bi-Directional Channels:** Real-time synchronization via WebSockets, Server-Sent Events (SSE), or realtime database listeners (Supabase/Firebase/Socket.io).

### 5-Second Timeline Toast Notifications (Right-to-Left Progress Bar)
- **Trigger Actions:** Critical feedback events (e.g. *"Added to Cart"*, *"Payment Successful"*, *"Booking Confirmed"*, *"Profile Updated"*).
- **5-Second Lifetime:** Pop-up toast automatically dismisses after exactly 5 seconds.
- **Visual Progress Bar Animation:** Features an animated progress timeline bar running along the bottom from **right to left** (indicating time remaining).
- **Interactive Controls:** Manual dismiss (`X`) button, pause timer on mouse hover / touch hold, accessible `aria-live="polite"` announcements.

### Notification Center & Top Navbar Bell Icon
- **Navbar Bell Icon:** Sticky top navbar integration featuring an animated unread badge counter.
- **Dual Storage:** Displays both **real-time instant notifications** and **stored persistent notifications**.
- **Notification Actions:** Per-item "Mark as Read", global "Mark All as Read", and clear history.
- **Categorization:** Tabs for Bookings, Security Alerts, Payment Receipts, and General Updates.

### Universal Authentication & Logout Controls
- **Universal Logout Button:** Highly visible and easily accessible for all authenticated users (present in the top navbar profile dropdown, user dashboard sidebar, and mobile menu).
- **Immediate Invalidation:** Clicking Logout immediately clears local session tokens, invalidates server session cookies, and smoothly redirects to the login screen.

### Account Lifecycle Management
- **Deactivate Account (Temporary Pause):**
  - Hides public profile and pauses recurring notifications.
  - Automatically terminates all active authentication sessions.
  - Preserves historical booking and order records.
  - Simple instant reactivation upon next verified login with automated security notification.
- **Delete Account (Permanent GDPR/CCPA Erasure):**
  - Requires re-authentication (password / passkey confirmation).
  - Explicit warning modal outlining irreversible data loss.
  - **Data Export Option:** Generates downloadable archive (`.zip` / `.json`) of personal data and transaction receipts before deletion.
  - **30-Day Safety Grace Period:** Account flagged for deletion with scheduled hard deletion from active databases and backups.

### Loyalty & Points Rewards System
- **Tiered Membership Levels:** Progression hierarchy (e.g., Bronze, Silver, Gold, Platinum VIP) with explicit perk milestones.
- **Points Ledger:** Complete audit trail of points earned, redeemed, pending, and expiring.
- **Checkout Redemption Integration:** Dynamic points slider at booking/checkout allowing split payments (Cash + Loyalty Points).
- **Milestone Rewards:** Automatic unlocking of exclusive privileges (complimentary breakfast, late check-out, suite upgrades).

### Cutting-Edge 2026 Features (Gemini Recommendations)
- **Passkey & Biometric Authentication:** WebAuthn / FIDO2 passwordless login (Touch ID, Face ID, Windows Hello) with zero phishable credentials.
- **Two-Factor Authentication (2FA / MFA):** TOTP authenticator app support (Google Authenticator, 1Password) with encrypted single-use recovery codes.
- **Global Command Palette (`Cmd+K` / `Ctrl+K`):** Fast keyboard-driven fuzzy search across pages, reservations, rooms, actions, and theme settings.
- **Granular Notification Management:** User-controlled matrix across channels (In-app, Push, Email, SMS) categorized by Security, Bookings, Concierge, and Offers.
- **Active Sessions & Device Security Manager:** Audit list of active sessions with device type, browser, IP address, approximate location, and a one-click "Revoke All Other Sessions" action.
- **Multi-Currency & Internationalization (i18n):** Real-time currency converter with live rates, RTL support (Arabic/Hebrew), and localized date/time formatting.
- **Offline Resilience & Optimistic UI:** Instant UI feedback on actions with background synchronization and resilient offline retry queues.
- **AI Concierge & Guest Voice/Chat Assistant:** On-device / edge streaming conversational assistant for room requests, local dining recommendations, and amenities booking with a strict zero-PII retention policy (prompts and voice streams never stored in training data or unencrypted logs).
- **Digital Key & Mobile Wallet Pass (NFC / BLE):** Contactless guest room access generating dynamic, hardware-encrypted NFC digital keys directly compatible with Apple Wallet and Google Wallet, with auto-expiring tokens tied to check-out timestamps.
- **Smart In-Room IoT Controls (WebSocket Real-Time Sync):** Unified room automation console controlling smart ambient lighting scenes, HVAC climate scheduling, motorized curtains, and digital privacy ("Do Not Disturb") indicators with instant multi-device live sync.
- **Algorithmic Dynamic Pricing & Yield Management:** Automated occupancy-driven revenue engine adjusting rates in real time based on demand velocity, lead time, seasonality, and local events, equipped with hard floor/ceiling margin guards.
- **Split Invoicing & Corporate Expense Billing:** Flexible multi-payer billing enabling guests to split folio costs (room charges to corporate account, incidental dining/spa to personal card) with automated VAT/GST tax compliance receipts.
- **Local-First Architecture & Conflict-Free Replicated Data Types (CRDTs):** Enables front-desk consoles and mobile guest clients to perform critical operations 100% offline during network interruptions, merging seamlessly without data conflicts via CRDTs upon reconnection.

---

## 7. Complete Page Suite Blueprint (Common & Advanced Pages)

A complete, production-grade application must deliver the following pages, designed without overlaps, emojis, or AI cliches:

### 1. Home / Landing Page
- High-impact value proposition hero with authentic imagery.
- Integrated real-time booking search bar (dates, guests, room type).
- Curated luxury room highlights with price-per-night and amenity tags.
- Interactive property amenities showcase (Spa, Dining, Pool, Concierge).
- Verified guest accolades and brand sustainability commitments.

### 2. Authentication & Verification Suite
- **Login & Register:** Split-screen layout, Passkey button, OAuth (Google, Apple), password strength indicator, remember device toggle.
- **Forgot Password & Reset Password:** Secure tokenized email flow with 60s resend cooldown countdown timer.
- **Two-Factor & Magic Link Entry:** Accessible 6-digit auto-advancing PIN input with paste support and backup code option.

### 3. Profile & Account Center
- **Personal Details:** Profile information, phone verification, avatar upload with client-side crop and preview.
- **Security Hub:** Password update, 2FA setup wizard, Passkey management, active device session revocation.
- **Preferences Panel:** Theme selector (Dark/Light/System), font scale slider, language/currency selectors, notification matrix.
- **Danger Zone:** Deactivate account modal and permanent account deletion wizard with data export.

### 4. User Dashboard
- Loyalty tier status card with current points balance and next-tier progress bar.
- Upcoming stay cards with check-in countdown, digital key status, and address/directions.
- Past stay history with one-click rebooking and downloadable PDF invoices.
- Quick concierge action buttons (Request room service, book spa, arrange airport transfer).
- **Dedicated Logout Button** in user dashboard header and navigation sidebar.

### 5. Admin Dashboard (Enterprise Operations & Real-Time Analytics)
- **Interactive Sales & Revenue Charts:**
  - Revenue and sales breakdown togglable by **Month**, **Week**, **Day**, and **Year**.
  - Interactive multi-axis charts: Line charts for revenue velocity, Bar charts for booking volume, and Donut charts for room-type distribution.
  - Occupancy rate analytics: Real-time gauge and historical trend comparison.
- **Interactive Room Inventory Calendar:**
  - Gantt-style timeline showing room occupancy with drag-and-drop reassignment and real-time live sync.
- **Comprehensive User Management Suite:**
  - Searchable, filterable, and paginated user list.
  - User details modal with full booking history, lifetime spend, and loyalty tier.
  - User account status controls: Activate, Deactivate, or Ban users.
  - Role-Based Access Control (RBAC): Assign Customer, Front Desk Staff, Manager, or Admin permissions.
- **Room & Inventory Manager:** Room status toggles (`Available`, `Occupied`, `Cleaning`, `Maintenance`), seasonal rate overrides.
- **Financial & Audit Logs:** Real-time transaction history and staff action audit log with CSV/Excel export.

### 6. Room & Product Catalog
- Sticky multi-parameter filter sidebar (date range, price range slider, capacity, view, amenities).
- Side-by-side room comparison drawer (compare up to 3 rooms simultaneously).
- Full-screen high-resolution photo gallery with accessible lightbox and virtual tour link.
- Transparent price calculation (nightly rate, taxes, service fee, refundable deposit).

### 7. Booking & Checkout Flow
- 3-step linear progress wizard (`Guest Details` → `Add-ons & Requests` → `Payment`).
- Curated add-on selections (Champagne on arrival, airport transfer, breakfast package).
- Stripe / Digital Wallet (Apple Pay / Google Pay) integrated payment form.
- Confirmed Booking Receipt page with printable PDF voucher and QR code for check-in.

### 8. Contact Us Page (with Functional Form)
- **Interactive Functional Contact Form:**
  - Form Fields: Full Name, Email Address, Phone Number, Department Selector (`General Concierge`, `Private Events & Weddings`, `Corporate Stays`, `Billing Support`), Subject, and Message.
  - Full client-side & server-side validation with inline error messages (zero element overlap).
  - Submit state: Button shows smooth loading spinner during submit; triggers 5-second RTL timeline toast on success.
- **Physical Concierge & Location:**
  - Interactive map embed with driving directions and transit routes.
  - Concierge desk direct telephone, email addresses, physical address with parking instructions.
  - Live WhatsApp concierge chat button.

### 9. Terms & Conditions Page
- Standalone, fully structured legal document with clear navigational index.
- Comprehensive sections: Acceptance of Terms, Booking & Guarantee Policies, Cancellation & Refunds, Guest Conduct, Liability, and Dispute Resolution.

### 10. About Us Page
- Architectural design philosophy and property heritage timeline.
- Executive leadership and master culinary chef profiles.
- Environmental sustainability, zero-waste initiatives, and community impact reports.

### 11. Reviews & Guest Testimonials Page
- Verified guest stay badge on every review.
- Category rating breakdown (Cleanliness, Comfort, Location, Service, Value).
- Interactive review submission modal with guest photo uploads and sub-category ratings.

### 12. System, Legal & Error Pages
- **404 Not Found & 500 Error Pages:** Collision-free, friendly recovery pages with search input and primary return-home action (no internal stack traces shown).
- **Legal Center:** Privacy Policy (GDPR/CCPA compliant), Terms & Conditions, and interactive Cookie Preference Center with granular tracking consent toggles.

### 13. FAQ & Intelligent Help Center Page
- Searchable interactive accordion with instant client-side fuzzy search across common questions.
- Categorized tabs: Reservations & Booking, Check-in / Digital Key, Dining & Room Service, Loyalty & Points, Billing & Cancellations.
- One-click escalation button linking directly to the Live Concierge WhatsApp / Chat or phone support.

### 14. Dining & Restaurant Reservation Page
- Interactive table booking widget (date, party size, seating area: Terrace, Main Dining Room, Private Chef's Counter).
- Full interactive digital menus with real-time dietary filters (Gluten-Free, Vegan, Halal, Nut-Free) and sommelier wine pairings.
- Special dietary requests and anniversary/celebration note inputs with server validation.

### 15. Spa & Wellness Experience Booking Page
- Curated luxury treatments catalog (Holistic Massages, Aromatherapy, Hydrotherapy, Facials) with durations and transparent pricing.
- Real-time time-slot picker with preferred therapist gender/specialist selection.
- Pre-treatment health questionnaire and cancellation policy agreement checkbox.

### 16. Events, Banquets & Conference Hall Page
- Interactive venue visualizer with 3D floor plan layouts (Theater, Classroom, U-Shape, Banquet).
- Dynamic attendee capacity calculator based on event type.
- Integrated Request for Proposal (RFP) submission form with event dates, expected guest count, audiovisual requirements, and catering preferences.

### 17. Loyalty Rewards Store & Redemption Portal
- Dedicated member rewards hub showing total point balance, redemption history, and tier progress.
- Rewards catalog: Complimentary suite upgrades, fine dining vouchers, late check-out passes, and airport limousine transfers.
- One-click instant point redemption with immediate voucher code and QR pass generation saved to user profile.

### 18. In-Stay Guest Services Hub (Digital Room Service & Housekeeping)
- Authenticated in-stay portal accessible via room Wi-Fi or mobile app:
  - Live digital room service ordering with real-time delivery countdown.
  - On-demand housekeeping requests (extra towels, feather pillows, turndown service, luggage collection).
  - One-tap Late Check-Out request with instant pricing and front-desk approval sync.

### 19. Invoices & Billing Center Page
- Itemized billing ledger tracking room rate, room service, minibar, spa charges, and applicable local taxes (VAT/GST/City Tax).
- Real-time split-billing management (assign items to corporate card vs. personal card).
- Downloadable cryptographically-signed PDF tax invoices for corporate expense filing.

### 20. Careers & Hospitality Culture Page
- Property culture statement, employee benefits showcase (health, education, travel discounts), and diversity commitments.
- Filterable open career listings by department (Front Office, Culinary, Housekeeping, Engineering, Management).
- Accessible multi-step job application form with CV/resume file upload, LinkedIn profile input, and privacy consent.

### 21. Press, Media & Brand Asset Kit Page
- Media inquiry press contact and official press release archive.
- Curated downloadable high-resolution media packs (WebP/AVIF imagery of suites, dining, and architecture).
- Official vector brand asset downloads (SVG logos, color palette specs, brand guidelines PDF).

### 22. Sustainability & Environmental Impact Dashboard
- Transparent property eco-ledger: Real-time energy conservation stats, solar generation output, and water recycling metrics.
- Zero-single-use-plastic initiative progress tracker.
- Guest voluntary carbon offset calculator at checkout supporting local reforestation projects.

---

## Golden Rule for the Coding Agent

> *"Before writing code, inspect the repository and identify the framework, dependencies, existing design system, authentication boundaries, and deployment process. Propose a concise plan. Implement in small, verifiable steps. Run tests, security checks, linting, and build. Fix failures rather than hiding them. Deliver maintainable, accessible software with evidence of testing. Never claim an app is production-ready or secure without verified proof. Never use emojis in the UI, and guarantee zero element overlaps across all screen sizes."*

---

# Skill: `instruction-tuning` (Sub-Agent Testing Protocol)

```yaml
---
name: instruction-tuning
description: Use sub-agents as test subjects to iteratively improve .claude/ instruction files. Run agent → inspect → fix instructions → re-run until agents follow the protocol correctly without hints.
---
```

> **DO NOT write memory files.** All learnings go into `.claude/rules/`, `.claude/agents/`, test-server code, or reference routes — NOT into memory.

### Mandatory Consent Check

Before starting, verify `.claude/user-consent.md` contains `ACCEPTED: true`. If missing, confirm:

1. **Terms of Service:** Confirm legal authorization to intercept target APIs.
2. **Autonomous Agents:** Acknowledge agents execute arbitrary code in worktrees.
3. **Resource Consumption:** Acknowledge token usage (50K–170K tokens/agent) and zombie process cleanup (`bash .claude/hooks/cleanup-agents.sh`).

### The 17-Step Tuning Loop

```text
1. Clean: bash .claude/hooks/cleanup-agents.sh
2. Verify commit: branch worktrees from latest committed instructions
3. Launch sub-agents with worktree isolation (max 8 concurrent)
4. Live monitor every 60s (read agent JSONL logs)
5. Stop agents when data is sufficient or stuck
6. Inspect: did they follow pipeline & elimination table?
7. Diagnose instruction gaps: "Would I do it this way?"
8. Fix instruction (generalized, not site-specific)
9. Consistency check across all .claude/ files
10. Prune redundant lines
11. Clean zombie processes
12. Fix infrastructure (browser crashes, server restarts)
13. Build utilities for repetitive operations
14. Add patterns to test-server
15. Commit fixes
16. Write handoff doc (.claude/tuning-handoff.md)
17. Start fresh session to clear stale context
```

---

---
name: task-observer
description: Meta-skill (rebelytics/one-skill-to-rule-them-all) that observes active work sessions, captures patterns, corrections, and judgment calls, and turns them into staged skill proposals.
---

# Meta-Skill: One Skill to Rule Them All (`task-observer`)

- **Source:** [github.com/rebelytics/one-skill-to-rule-them-all](https://github.com/rebelytics/one-skill-to-rule-them-all)
- **Author:** Rebelytics (Stephen Thoemmes & contributors)
- **License:** CC BY 4.0 (Augmented Expertise Methodology)

> *"The meta-skill that builds and improves all your skills, including itself."*  
> Observes active work sessions, captures patterns, corrections, and judgment calls, and turns them into staged skill proposals for human review.

### Why Task Observer?

1. **Discovers New Skills:** Spots repetitive manual actions and drafts skill candidates.
2. **Evolves Existing Skills:** Notices user corrections and refines skill instructions.
3. **Self-Improving Loop:** Evaluates its own observation logs and enhances its detection heuristics.
4. **Cross-Cutting Principles:** Extracts universal rules enforced across the whole skill library.
5. **Human Control:** Generates staged proposals; never silently overwrites live skills.

### Installation

```bash
# Via Skills CLI:
npx skills add rebelytics/one-skill-to-rule-them-all --skill task-observer -g

# Or manual clone:
git clone https://github.com/rebelytics/one-skill-to-rule-them-all.git
cp -r one-skill-to-rule-them-all/.claude/skills/task-observer ~/.claude/skills/
```

---

# The 10 Must-Have Skills for Claude Code in 2026

---
name: frontend-design
description: Production-grade UI generation escaping generic AI defaults with distinctive aesthetics, bold typography pairings, and accessible design systems.
---

### 1. frontend-design
- **Source:** [github.com/anthropics/skills](https://github.com/anthropics/skills) (277K+ installs, ~65.8k stars)
- **Primary Value:** Escapes "distributional convergence" (Inter font defaults, purple gradients, generic bento grids). Creates intentional, human-crafted visual direction.
- **Install Command:**
```bash
npx skills add anthropics/claude-code --skill frontend-design
```

---
name: browser-use
description: Live headless and visible web automation, browser navigation, interactive form testing, and screenshot verification.
---

### 2. browser-use
- **Source:** [github.com/browser-use/browser-use](https://github.com/browser-use/browser-use)
- **Primary Value:** Autonomous web browsing agent capable of clicking, filling inputs, navigating multi-step web flows, and capturing visual screenshots for validation.
- **Install Command:**
```bash
npx skills add https://github.com/browser-use/browser-use --skill browser-use
```

---
name: simplify
description: Automated code review and simplification skill that polishes first-draft implementations into clean, maintainable, second-draft production code.
---

### 3. simplify (Code Reviewer)
- **Source:** Official Anthropic Skill
- **Primary Value:** Automatically reviews recently written code, prunes redundant logic, flattens nesting, removes dead code, and ensures consistent idiomatic design.
- **Install Command:**
```bash
npx skills add anthropics/claude-code --skill simplify
```

---
name: remotion
description: React-based programmatic video creation and rendering skill for dynamic motion graphics, presentations, and algorithmic video generation.
---

### 4. remotion
- **Source:** [github.com/remotion-dev/remotion](https://github.com/remotion-dev/remotion)
- **Primary Value:** Build frame-accurate videos programmatically using standard React components, CSS, and SVG canvas APIs.
- **Install Command:**
```bash
npx skills add remotion/agent-skills
```

---
name: google-workspace
description: Unified CLI and MCP integration for 50+ Google Workspace APIs including Drive, Docs, Sheets, Gmail, and Calendar automation.
---

### 5. google-workspace (GWS)
- **Source:** [github.com/googleworkspace/cli](https://github.com/googleworkspace/cli) (~4.9k stars)
- **Primary Value:** Comprehensive automation for documents, spreadsheets, inbox processing, and calendar schedules directly through AI agent workflows.
- **Install Command:**
```bash
npm install -g @googleworkspace/cli
```

---
name: valyu
description: Real-time specialized web search and retrieval skill accessing 36+ deep research, academic, financial, and paywalled data sources.
---

### 6. valyu
- **Source:** [github.com/valyuai/skills](https://github.com/valyuai/skills)
- **Primary Value:** High-precision research queries accessing specialized academic papers, financial databases, and verified factual repositories.
- **Install Command:**
```bash
npx skills add https://github.com/valyuai/skills --skill valyu-best-practices
```

---
name: antigravity-awesome-skills
description: Universal cross-agent skills directory and installer providing access to 1,234+ curated AI coding skills across all development stacks.
---

### 7. antigravity-awesome-skills
- **Source:** Universal Skill Catalog (~22k+ stars)
- **Primary Value:** Discovers, searches, and installs skills across frameworks, programming languages, and specialized development tools.
- **Install Command:**
```bash
npx antigravity-awesome-skills --claude
```

---
name: planetscale
description: Git-style database schema branching, indexing analysis, N+1 query safety, and zero-downtime migration workflows.
---

### 8. planetscale
- **Source:** Official PlanetScale Skill
- **Primary Value:** Validates query performance, suggests optimal database indexing, detects dangerous N+1 queries, and coordinates safe zero-downtime schema migrations.
- **Install Command:**
```bash
npx skills add planetscale/agent-skill
```

---
name: shannon
description: Autonomous AI penetration testing skill providing Docker-isolated adversarial security auditing and automated exploit verification.
---

### 9. shannon
- **Source:** [github.com/KeygraphHQ/shannon](https://github.com/KeygraphHQ/shannon)
- **Primary Value:** Autonomous red-team penetration testing in Docker environments with a 96.15% exploit validation rate against OWASP vulnerabilities.
- **Install Command:**
```bash
npx skills add unicodeveloper/shannon
```

---
name: excalidraw-diagram
description: Executable visual software architecture diagram generator using Playwright rendering and self-validating diagram code.
---

### 10. excalidraw-diagram
- **Source:** [github.com/coleam00/excalidraw-diagram-skill](https://github.com/coleam00/excalidraw-diagram-skill)
- **Primary Value:** Generates clean, hand-drawn-style architectural schematics, sequence diagrams, and flowcharts with live Playwright verification.
- **Install Command:**
```bash
npx skills add https://github.com/coleam00/excalidraw-diagram-skill --skill excalidraw-diagram
```

---

# Top 8 Claude Skills for UI/UX Engineers

---
name: vercel-web-design-guidelines
description: Automated 100+ rule audit skill checking accessibility, UX patterns, HTML5 semantics, and modern web interface standards.
---

### 1. vercel-web-design-guidelines
- **Source:** [github.com/vercel-labs/agent-skills](https://github.com/vercel-labs/agent-skills) (~19.5k stars)
- **Primary Value:** Evaluates frontend code against 100+ strict accessibility, usability, layout stability, and semantic HTML rules.
- **Install Command:**
```bash
npx skills add vercel-labs/web-interface-guidelines
```

---
name: vercel-react-best-practices
description: 57 prioritized rules for React and Next.js performance, eliminating bundle bloat, watermarking waterfalls, and layout shifts.
---

### 2. vercel-react-best-practices
- **Source:** [github.com/vercel-labs/agent-skills](https://github.com/vercel-labs/agent-skills) (~19.5k stars)
- **Primary Value:** Enforces 57 prioritized performance optimizations across Next.js App Router, React Server Components, and client rendering.
- **Install Command:**
```bash
npx skills add vercel/react-best-practices
```

---
name: vercel-composition-patterns
description: Component architecture skill for flexible composition patterns, slotting, and eliminating boolean prop anti-patterns.
---

### 3. vercel-composition-patterns
- **Source:** [github.com/vercel-labs/agent-skills](https://github.com/vercel-labs/agent-skills) (~19.5k stars)
- **Primary Value:** Architectural refactoring eliminating multi-boolean prop pollution by introducing composable slot patterns and child inversion of control.
- **Install Command:**
```bash
npx skills add vercel-labs/agent-skills --skill composition-patterns
```

---
name: ui-ux-pro-max
description: Multi-style design system database providing 50 distinct aesthetic styles, 97 color palettes, and CLI-assisted design scaffolding.
---

### 4. ui-ux-pro-max
- **Source:** [github.com/nextlevelbuilder/ui-ux-pro-max-skill](https://github.com/nextlevelbuilder/ui-ux-pro-max-skill) (~29.6k stars)
- **Primary Value:** Instant design system generator covering 50 unique aesthetic genres, typography hierarchies, and cohesive color palettes.
- **Install Command:**
```bash
npx skills add nextlevelbuilder/ui-ux-pro-max-skill
```

---
name: bencium-ux-designer
description: Dual-mode UX architecture skill supporting both innovative experimental design and controlled enterprise UX patterns.
---

### 5. bencium-ux-designer
- **Source:** [github.com/bencium/bencium-claude-code-design-skill](https://github.com/bencium/bencium-claude-code-design-skill)
- **Primary Value:** Switches dynamically between "Innovative Mode" (bold, tactile editorial layouts) and "Controlled Mode" (rigorous enterprise dashboards).
- **Install Command:**
```bash
npx skills add bencium/bencium-claude-code-design-skill
```

---
name: accesslint
description: Dedicated accessibility auditing skill with WCAG 2.1 contrast checking, keyboard navigation verification, and screen reader simulation.
---

### 6. accesslint
- **Source:** [github.com/accesslint/claude-marketplace](https://github.com/accesslint/claude-marketplace)
- **Primary Value:** Audits DOM contrast ratios, missing ARIA landmark attributes, focus traps, and keyboard accessibility before deployment.
- **Install Command:**
```bash
npx skills add accesslint/claude-marketplace
```

---
name: react-native-skills
description: Mobile UI performance engineering skill focusing on React Native, Expo, FlashList, 60fps gesture animations, and native bridge optimization.
---

### 7. react-native-skills
- **Source:** [github.com/vercel-labs/agent-skills](https://github.com/vercel-labs/agent-skills) (~19.5k stars)
- **Primary Value:** Mobile-first performance engineering for React Native and Expo applications, optimizing list rendering, memory usage, and native thread communication.
- **Install Command:**
```bash
git clone https://github.com/vercel-labs/agent-skills.git
cp -r agent-skills/skills/react-native-skills ~/.claude/skills/
```

---

# Curated Workflow & Infrastructure Skills

---
name: superpowers
description: Structured TDD software development workflow enforcing clarity, specification, step-by-step planning, test-driven execution, and review.
---

### 1. superpowers
- **Source:** [github.com/obra/superpowers](https://github.com/obra/superpowers) (~40,900 stars)
- **Primary Value:** Enforces the rigorous 5-step engineering lifecycle: `clarify` → `spec` → `plan` → `execute` → `review` with strict test-driven development.
- **Install Command:**
```bash
/plugin marketplace add obra/superpowers-marketplace
/plugin install superpowers@superpowers-marketplace
```

---
name: spartan-ai-toolkit
description: Strict multi-profile quality gate pipeline enforcing typecheck, lint, test, and automated code review across 8 stack profiles.
---

### 2. spartan-ai-toolkit
- **Source:** [github.com/spartan-stratos/spartan-ai-toolkit](https://github.com/spartan-stratos/spartan-ai-toolkit)
- **Primary Value:** Hardens CI/CD pipelines with automated multi-stack quality verification gates (`typecheck` → `lint` → `test` → `review`).
- **Install Command:**
```bash
npx @c0x12c/ai-toolkit@latest --local
```

---
name: mattpocock-skills
description: TypeScript mastery, PRD writing, structured refactoring plans, and Git guardrails for coding agents.
---

### 3. mattpocock-skills
- **Source:** [github.com/mattpocock/skills](https://github.com/mattpocock/skills)
- **Primary Value:** Strict TypeScript type-safety rules, automated product requirement document (PRD) creation, and safe Git branch guardrails.
- **Install Command:**
```bash
npx skills@latest add mattpocock/skills/write-a-prd
npx skills@latest add mattpocock/skills/request-refactor-plan
npx skills@latest add mattpocock/skills/git-guardrails-claude-code
```

---
name: terrashark
description: Lightweight Terraform assistant grounded in HashiCorp best practices, modular infrastructure as code, and security drift detection.
---

### 4. terrashark
- **Source:** [github.com/LukasNiessen/terrashark](https://github.com/LukasNiessen/terrashark)
- **Primary Value:** Terraform infrastructure-as-code generation adhering to HashiCorp security patterns, state-locking, and drift prevention.
- **Install Command:**
```bash
/plugin marketplace add LukasNiessen/terrashark
/plugin install terrashark
```

---

# Advanced Security & DevSecOps Engineering Skills

---
name: trivy-container-security
description: Comprehensive container image, filesystem, SBOM, and Kubernetes misconfiguration vulnerability scanner.
---

### 1. trivy-container-security
- **Source:** [github.com/aquasecurity/trivy](https://github.com/aquasecurity/trivy) (~25k stars)
- **Primary Value:** Scans Docker container base images, OS packages, and application dependencies for known CVEs before deployment. Generates CycloneDX / SPDX Software Bill of Materials (SBOM).
- **Install Command:**
```bash
npx skills add aquasecurity/trivy
```

---
name: spectral-secret-guard
description: High-speed automated secret and credential scanner with pre-commit git hooks and CI/CD secret leakage detection.
---

### 2. spectral-secret-guard
- **Source:** SpectralOps / Check Point
- **Primary Value:** Prevents developers and CI/CD pipelines from committing API keys, tokens, certificates, and private signing credentials into source control.
- **Install Command:**
```bash
npx skills add spectralops/spectral-ci
```

---
name: schemathesis-api-fuzzer
description: Specification-based property testing tool for OpenAPI and GraphQL APIs that generates negative inputs and edge-case fuzzing payloads.
---

### 3. schemathesis-api-fuzzer
- **Source:** [github.com/schemathesis/schemathesis](https://github.com/schemathesis/schemathesis) (~2.5k stars)
- **Primary Value:** Automated API contract compliance verification and negative security fuzzing. Discovers server crashes, 500 errors, schema mismatches, and authorization boundary leaks.
- **Install Command:**
```bash
npx skills add schemathesis/schemathesis
```

---
name: cosign-artifact-integrity
description: Container signing, verification, and supply chain security tool using Sigstore and keyless cryptographic signing.
---

### 4. cosign-artifact-integrity
- **Source:** [github.com/sigstore/cosign](https://github.com/sigstore/cosign) (~4.8k stars)
- **Primary Value:** Signs web production bundles, container images, and Android APK artifacts using Sigstore; verifies release provenance and prevents supply-chain tampering.
- **Install Command:**
```bash
npx skills add sigstore/cosign
```

---

# Professional Developer 100% Production Skills

---
name: database-architecture-and-migrations
description: Production-grade relational database architecture, ACID transactions, Prisma and Drizzle schema migrations, connection pooling, and deterministic seeders.
---

### 1. database-architecture-and-migrations
- **Source:** [prisma/prisma](https://github.com/prisma/prisma) (~39k stars) & [drizzle-team/drizzle-orm](https://github.com/drizzle-team/drizzle-orm) (~36k stars)
- **Primary Value:** Generates robust, zero-downtime relational schemas (PostgreSQL / MySQL / SQLite), migration rollbacks, connection pool tuning (PgBouncer), and idempotent database seed scripts. Eliminates data corruption, N+1 queries, and schema drift.
- **Install & Run Commands:**
```bash
pnpm add -D prisma
pnpm dlx prisma init --datasource-provider postgresql
pnpm dlx prisma migrate dev --name init_schema
pnpm dlx prisma db seed
```

---
name: tanstack-query-state-sync
description: Resilient server-state caching, background revalidation, optimistic UI mutations, race condition cancellation, and offline cache persistence using TanStack Query.
---

### 2. tanstack-query-state-sync
- **Source:** [github.com/TanStack/query](https://github.com/TanStack/query) (~44k stars)
- **Primary Value:** Eliminates waterfall queries, handles stale-while-revalidate caching, coordinates optimistic UI updates with automatic rollbacks on network failure, and keeps client state synchronized across browser tabs and devices.
- **Install & Setup Commands:**
```bash
pnpm add @tanstack/react-query @tanstack/react-query-persist-client
pnpm add -D @tanstack/eslint-plugin-query
```

---
name: playwright-e2e-testing
description: End-to-end automation, mobile emulation, visual screenshot regression, network interception, and CI/CD test harness with Playwright.
---

### 3. playwright-e2e-testing
- **Source:** [github.com/microsoft/playwright](https://github.com/microsoft/playwright) (~70k stars)
- **Primary Value:** Cross-browser end-to-end verification (Chromium, Firefox, WebKit, Mobile Safari, Mobile Chrome). Executes automated smoke tests, visual regression snapshot diffing, and authenticated flow tests with zero flakiness.
- **Install & Run Commands:**
```bash
npm init playwright@latest -- --yes --browsers=all
npx playwright test
npx playwright test --ui
```

---
name: trpc-typed-api-contracts
description: End-to-end type safety between backend and frontend/mobile clients, schema-validated procedures (Zod), and automated query batching without code generation.
---

### 4. trpc-typed-api-contracts
- **Source:** [github.com/trpc/trpc](https://github.com/trpc/trpc) (~36k stars)
- **Primary Value:** Guarantees 100% type safety across network boundaries. Breaking backend API changes trigger immediate compile-time errors in frontend/mobile components before deployment, eliminating runtime schema mismatches.
- **Install & Setup Commands:**
```bash
pnpm add @trpc/server @trpc/client @trpc/react-query zod
```

---
name: opentelemetry-observability
description: Distributed tracing, structured Pino JSON logging, OpenTelemetry metrics, Sentry error monitoring, and container health probes.
---

### 5. opentelemetry-observability
- **Source:** [open-telemetry/opentelemetry-js](https://github.com/open-telemetry/opentelemetry-js) (~4.5k stars) & [getsentry/sentry-javascript](https://github.com/getsentry/sentry-javascript) (~10k stars)
- **Primary Value:** Provides instant root-cause analysis in production with distributed trace IDs, high-performance structured logging without memory leaks, and automated alerts for unhandled exceptions and performance bottlenecks.
- **Install & Setup Commands:**
```bash
pnpm add @opentelemetry/api @opentelemetry/sdk-node pino pino-pretty @sentry/nextjs
```

---
name: docker-production-runtime
description: Multi-stage, non-root container packaging, Docker Compose orchestrations, automated health checks, and Caddy reverse-proxy SSL automation.
---

### 6. docker-production-runtime
- **Source:** Docker & Cloud Native Computing Foundation (CNCF)
- **Primary Value:** Creates deterministic, lean, production-ready container images with minimal attack surfaces (Distroless / Alpine non-root users), automated healthcheck probes, and zero host environment contamination.
- **Install & Run Commands:**
```bash
docker compose up --build -d
docker compose ps
docker compose logs -f app
```

---
name: storybook-design-system
description: Isolated component development environment, visual regression testing, design token synchronization, and automated WCAG accessibility auditing with axe-core.
---

### 7. storybook-design-system
- **Source:** [github.com/storybookjs/storybook](https://github.com/storybookjs/storybook) (~84k stars)
- **Primary Value:** Allows frontend engineers to develop, stress-test, and document UI components in complete isolation across every screen size and state (empty, loading, error, hover, disabled) with automated a11y checks.
- **Install & Run Commands:**
```bash
npx storybook@latest init --yes
pnpm add -D @storybook/addon-a11y @storybook/test
npm run storybook
```

---
name: performance-bundle-optimizer
description: Bundle size profiling, route-based code splitting, Core Web Vitals optimization (LCP, INP, CLS), and modern asset compression pipelines.
---

### 8. performance-bundle-optimizer
- **Source:** [vercel/next.js bundle-analyzer](https://github.com/vercel/next.js) & [vite-bundle-visualizer](https://github.com/btd/rollup-plugin-visualizer)
- **Primary Value:** Audits bundle sizes, eliminates dead code / bloated dependencies, enforces code splitting with dynamic `import()`, optimizes fonts and WebP/AVIF images, and guarantees sub-second page loads (LCP < 2.5s, INP < 200ms, CLS < 0.1).
- **Install & Run Commands:**
```bash
pnpm add -D @next/bundle-analyzer
ANALYZE=true pnpm build
```

---

# Universal Core Developer Skills (Used Daily by 90%+ of Developers)

---
name: git-mastery-and-conventional-commits
description: Standard Git version control mastery, Conventional Commits specification, trunk-based/GitFlow branching, interactive rebase, safe undo strategies, and Husky pre-commit hooks.
---

### 1. git-mastery-and-conventional-commits
- **Source:** [git-scm.com](https://git-scm.com/) & [conventionalcommits.org](https://www.conventionalcommits.org/)
- **Primary Value:** Enforces standardized git commit history, automated changelog generation, clean linear histories with interactive rebasing, safe stash/reflog recovery, and automated pre-commit linting.
- **Conventional Commits Standard:**
  - `feat:` New user-facing feature (e.g., `feat(auth): add passkey biometric login support`)
  - `fix:` Bug fix (e.g., `fix(booking): prevent double-charge on flaky network retries`)
  - `refactor:` Code change that neither fixes a bug nor adds a feature (e.g., `refactor(db): extract user repository layer`)
  - `perf:` Performance optimization (e.g., `perf(images): migrate hero banners to AVIF format`)
  - `test:` Adding or correcting tests (e.g., `test(e2e): add playwright checkout suite`)
  - `chore:` Maintenance tasks, dependency updates, tooling (e.g., `chore(deps): update prisma to v5.12`)
  - `docs:` Documentation changes only (e.g., `docs(readme): add docker setup instructions`)
  - `ci:` CI/CD pipeline modifications (e.g., `ci(github): add automated typecheck step`)
- **Essential Git Commands:**
```bash
# Branching & feature flow
git checkout -b feature/room-booking-flow
git branch -d feature/old-branch                  # Safe delete
git branch -D feature/stale-branch                # Force delete

# Clean commits & interactive rebase
git add -p                                        # Review & stage hunks interactively
git commit -m "feat(api): implement room reservation endpoint"
git rebase -i HEAD~3                              # Squash, reword, or fixup past commits
git commit --amend --no-edit                      # Add staged changes to previous commit

# Safety nets & recovery
git stash push -m "WIP: payment refactor"         # Stash with descriptive message
git stash pop                                     # Restore stashed changes
git reflog                                        # View full history of HEAD moves (recover deleted commits)
git reset --soft HEAD~1                           # Undo last commit, keep changes staged
git revert <commit-hash>                          # Create safe inverse commit for pushed history
```
- **Automated Pre-Commit Quality Gate Setup (Husky + lint-staged + commitlint):**
```bash
pnpm add -D husky lint-staged @commitlint/cli @commitlint/config-conventional
npx husky init
echo "pnpm lint-staged" > .husky/pre-commit
echo "npx --no -- commitlint --edit \$1" > .husky/commit-msg
```

---
name: unit-and-integration-testing-suite
description: Comprehensive unit & integration testing framework utilizing Vitest/Jest, React Testing Library (RTL), Mock Service Worker (MSW v2), and the AAA pattern.
---

### 2. unit-and-integration-testing-suite
- **Source:** [vitest.dev](https://vitest.dev/) & [testing-library.com](https://testing-library.com/) & [mswjs.io](https://mswjs.io/)
- **Primary Value:** Guarantees code correctness, prevents regressions, tests accessibility and user behavior instead of implementation details, and mocks external network calls reliably.
- **Core Testing Principles:**
  - **AAA Pattern:** Arrange (setup data & mocks), Act (execute code or trigger user event), Assert (verify expected behavior).
  - **Testing Trophy:** Favor integration tests over unit tests; test components the way real users interact with them.
  - **Zero Implementation Testing:** Never test private variables, internal component state, or CSS class names. Query by user-facing roles: `screen.getByRole('button', { name: /reserve room/i })`.
- **Install & Setup Commands:**
```bash
pnpm add -D vitest @testing-library/react @testing-library/user-event @testing-library/jest-dom msw jsdom
```
- **Standard Test Example (Vitest + RTL + MSW):**
```typescript
import { render, screen } from '@testing-library/react';
import userEvent from '@testing-library/user-event';
import { expect, test, describe } from 'vitest';
import { BookingForm } from './BookingForm';

describe('BookingForm Integration', () => {
  test('submits reservation and displays confirmation', async () => {
    const user = userEvent.setup();
    render(<BookingForm roomId="room-402" />);

    // Arrange & Act
    await user.type(screen.getByRole('textbox', { name: /guest name/i }), 'Sophia Laurent');
    await user.click(screen.getByRole('button', { name: /confirm reservation/i }));

    // Assert
    expect(await screen.findByText(/reservation confirmed/i)).toBeInTheDocument();
  });
});
```

---
name: rest-api-architecture-and-openapi
description: Production RESTful API architectural standards, predictable URL naming conventions, HTTP status codes, cursor pagination, and OpenAPI 3.1 / Swagger documentation.
---

### 3. rest-api-architecture-and-openapi
- **Source:** [OpenAPI 3.1 Spec](https://www.openapis.org/) & [REST API Guidelines](https://github.com/microsoft/api-guidelines)
- **Primary Value:** Eliminates unpredictable endpoints, enforces uniform response envelopes, enables automated client generation, and documents API schemas with interactive Swagger UI.
- **RESTful Design Conventions:**
  - **Nouns over Verbs:** `/api/v1/rooms` (GET/POST), `/api/v1/rooms/:id` (GET/PATCH/DELETE), `/api/v1/rooms/:id/bookings` (sub-resources).
  - **HTTP Verbs:** `GET` (safe, idempotent read), `POST` (create non-idempotent), `PUT` (full replace idempotent), `PATCH` (partial update), `DELETE` (remove idempotent).
  - **Status Codes:**
    - `200 OK` (standard success) | `201 Created` (resource created with `Location` header) | `204 No Content` (deletion)
    - `400 Bad Request` (schema failure) | `401 Unauthorized` (missing/expired token) | `403 Forbidden` (insufficient role)
    - `404 Not Found` (missing resource) | `409 Conflict` (duplicate entry / race condition) | `429 Too Many Requests` (rate limited)
    - `500 Internal Server Error` (unhandled server failure masked from user)
  - **Pagination Standard:** Use cursor-based pagination for high volume (`?cursor=eyJpZCI6MTB9&limit=20`) to prevent offset-drift.
- **Install & Generation Commands:**
```bash
pnpm add @asteasolutions/zod-to-openapi swagger-ui-express
```

---
name: github-actions-ci-cd-automation
description: Robust GitHub Actions CI/CD workflows, automated matrix testing, dependency caching, bundle size gates, and automated preview/production deployments.
---

### 4. github-actions-ci-cd-automation
- **Source:** [GitHub Actions Documentation](https://docs.github.com/en/actions)
- **Primary Value:** Automates quality checks on every Pull Request, prevents broken code from merging to main, speeds up feedback loops with aggressive cache layers, and deploys reliably to production.
- **Production CI Pipeline Blueprint (`.github/workflows/ci.yml`):**
```yaml
name: CI Quality Gate

on:
  push:
    branches: [main]
  pull_request:
    branches: [main]

concurrency:
  group: ${{ github.workflow }}-${{ github.ref }}
  cancel-in-progress: true

jobs:
  validate:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - uses: pnpm/action-setup@v3
        with:
          version: 9
      - uses: actions/setup-node@v4
        with:
          node-version: 20
          cache: 'pnpm'

      - name: Install Dependencies
        run: pnpm install --frozen-lockfile

      - name: Lint & Formatting
        run: pnpm run lint

      - name: Typecheck
        run: pnpm run typecheck

      - name: Run Tests
        run: pnpm run test:coverage

      - name: Build Application
        run: pnpm run build
```

---
name: clean-code-solid-and-design-patterns
description: Practical SOLID architecture principles, essential GoF design patterns (Factory, Repository, Strategy, Adapter), code smell eradication, and readable refactoring patterns.
---

### 5. clean-code-solid-and-design-patterns
- **Source:** [Clean Code Architecture](https://blog.cleancoder.com/) & Refactoring Standards
- **Primary Value:** Prevents spaghetti code, minimizes technical debt, and ensures code is maintainable, decoupled, and straightforward for any engineer to extend without breaking existing modules.
- **The 5 SOLID Principles in Practice:**
  1. **Single Responsibility (SRP):** A class or module should have one, and only one, reason to change. Separate business calculations from database persistence and HTTP formatting.
  2. **Open/Closed (OCP):** Open for extension, closed for modification. Implement new payment processors via an interface/strategy rather than modifying giant `switch(type)` statements.
  3. **Liskov Substitution (LSP):** Subtypes must be substitutable for their base types without altering system correctness.
  4. **Interface Segregation (ISP):** Clients should not be forced to depend upon interfaces they do not use. Split fat interfaces into fine-grained role interfaces (`ReadableRepository`, `WritableRepository`).
  5. **Dependency Inversion (DIP):** Depend upon abstractions, not concretions. Inject repository interfaces into services, making them easily mockable in tests.
- **Top 4 Design Patterns Every Developer Uses:**
  - **Repository Pattern:** Encapsulates database queries behind domain methods (`userRepo.findById(id)`).
  - **Strategy Pattern:** Interchangeable algorithms (e.g. `PaymentStrategy` with `StripePayment` and `PayPalPayment`).
  - **Factory Pattern:** Encapsulates complex object creation logic.
  - **Adapter Pattern:** Translates incompatible third-party API data structures into internal domain types.

---
name: systematic-debugging-and-profiling
description: Scientific 5-step debugging method, memory leak identification, Chrome DevTools profiling, Node.js heap inspection, and network bottleneck isolation.
---

### 6. systematic-debugging-and-profiling
- **Source:** Chrome DevTools & Node.js Diagnostic Workgroup
- **Primary Value:** Replaces chaotic "trial-and-error" guessing with a repeatable, scientific protocol that rapidly locates root causes, solves memory leaks, and fixes elusive race conditions.
- **The 5-Step Scientific Debugging Protocol:**
  1. **Reproduce:** Create an isolated, deterministic minimal reproduction script or failing unit test.
  2. **Isolate:** Binary-search the stack (git bisect, component isolation) to identify the exact line or mutation point.
  3. **Hypothesize:** Formulate a testable hypothesis ("The event listener in `RoomCard` is not cleaned up on unmount, holding 5MB in heap memory").
  4. **Experiment:** Test the hypothesis using targeted breakpoints or heap snapshot diffs.
  5. **Fix & Guard:** Fix the root cause and add an automated regression test so the defect can never reappear.
- **Diagnostic Commands & Tools:**
```bash
# Node.js inspection & profiling
node --inspect-brk dist/index.js                 # Debug with Chrome DevTools attached
node --trace-warnings dist/index.js               # Trace uncaught promise warnings
npx clinic doctor -- node dist/index.js          # Diagnose event loop delay & I/O bottlenecks

# Git Bisect (find the exact commit that introduced a bug)
git bisect start
git bisect bad HEAD                               # Current version has bug
git bisect good v1.4.0                            # Past version was good
# Git automatically checks out commits; test and run `git bisect good` or `bad`
```

---
name: env-config-and-secrets-hygiene
description: 12-Factor App configuration standard, type-safe environment variable parsing with Zod / @t3-oss/env-core, layered .env environments, and zero credential leakage.
---

### 7. env-config-and-secrets-hygiene
- **Source:** [12factor.net/config](https://12factor.net/config) & [t3-oss/env-core](https://env.t3.gg/)
- **Primary Value:** Prevents missing environment variable crashes at runtime, validates URLs and database connection formats at application boot, and ensures secrets never leak into source code or browser bundles.
- **Install & Setup:**
```bash
pnpm add @t3-oss/env-nextjs zod
# Or for standard Node.js / Vite:
pnpm add @t3-oss/env-core zod
```
- **Type-Safe Env Schema (`src/env.ts`):**
```typescript
import { createEnv } from "@t3-oss/env-nextjs";
import { z } from "zod";

export const env = createEnv({
  server: {
    DATABASE_URL: z.string().url(),
    NODE_ENV: z.enum(["development", "test", "production"]).default("development"),
    JWT_SECRET: z.string().min(32),
  },
  client: {
    NEXT_PUBLIC_APP_URL: z.string().url(),
  },
  runtimeEnv: {
    DATABASE_URL: process.env.DATABASE_URL,
    NODE_ENV: process.env.NODE_ENV,
    JWT_SECRET: process.env.JWT_SECRET,
    NEXT_PUBLIC_APP_URL: process.env.NEXT_PUBLIC_APP_URL,
  },
});
```

---
name: monorepo-and-workspace-orchestration
description: High-efficiency monorepo management with pnpm workspaces and Turborepo, parallel caching, cross-package dependency resolution, and SemVer versioning.
---

### 8. monorepo-and-workspace-orchestration
- **Source:** [pnpm.io/workspaces](https://pnpm.io/workspaces) & [turbo.build](https://turbo.build/)
- **Primary Value:** Speeds up build times by 10x with smart dependency graph caching, enables clean code sharing across web, mobile, and backend apps, and simplifies multi-package dependency maintenance.
- **Install & Setup Commands:**
```bash
pnpm add -D -w turbo
npx turbo init
```
- **Everyday Workspace Commands:**
```bash
# Targeted workspace execution
pnpm --filter @hotel/web dev                      # Start only web app
pnpm --filter @hotel/api build                    # Build only backend API
pnpm --recursive run lint                         # Run linting across all packages
pnpm dedupe                                       # Deduplicate identical dependencies

# Turborepo turbo pipelines
turbo run build test lint                         # Execute with parallel cached pipeline
turbo run dev --parallel                          # Run dev servers concurrently
```

---

## Master Command Cheat Sheet

```bash
# --- Daily Core Developer Essentials ---
pnpm add -D husky lint-staged @commitlint/cli @commitlint/config-conventional
pnpm add -D vitest @testing-library/react @testing-library/user-event msw
pnpm add @asteasolutions/zod-to-openapi swagger-ui-express
pnpm add @t3-oss/env-nextjs zod
pnpm add -D -w turbo

# --- Workflow & Quality Gates ---
/plugin marketplace add obra/superpowers-marketplace
/plugin install superpowers@superpowers-marketplace
npx @c0x12c/ai-toolkit@latest --local
npx skills add anthropics/claude-code --skill simplify

# --- Frontend & UI/UX (100% AI-Free Design) ---
npx skills add anthropics/claude-code --skill frontend-design
npx skills add vercel/react-best-practices
npx skills add vercel-labs/web-interface-guidelines
npx skills add nextlevelbuilder/ui-ux-pro-max-skill
npx skills add bencium/bencium-claude-code-design-skill
npx skills add accesslint/claude-marketplace
npx storybook@latest init --yes

# --- Mobile (React Native / Expo) ---
git clone https://github.com/vercel-labs/agent-skills.git
cp -r agent-skills/skills/react-native-skills ~/.claude/skills/

# --- Meta-Skills & Evolution ---
npx skills add rebelytics/one-skill-to-rule-them-all --skill task-observer -g

# --- Full-Stack Production & Data Architecture ---
pnpm dlx prisma init --datasource-provider postgresql
pnpm add @tanstack/react-query @tanstack/react-query-persist-client
pnpm add @trpc/server @trpc/client @trpc/react-query zod

# --- End-to-End Testing & Observability ---
npm init playwright@latest -- --yes --browsers=all
pnpm add @opentelemetry/api @opentelemetry/sdk-node pino @sentry/nextjs
pnpm add -D @next/bundle-analyzer

# --- Security, Pentesting & DevSecOps ---
npx skills add unicodeveloper/shannon
npx skills add aquasecurity/trivy
npx skills add spectralops/spectral-ci
npx skills add schemathesis/schemathesis
npx skills add sigstore/cosign

# --- Diagrams & Media ---
npx skills add https://github.com/coleam00/excalidraw-diagram-skill --skill excalidraw-diagram
npx skills add remotion/agent-skills

# --- Universal Catalog (1,234+ Skills) ---
npx antigravity-awesome-skills --claude
```
