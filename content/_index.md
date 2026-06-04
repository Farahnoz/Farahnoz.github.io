+++
title = "Vasil Abdul Razak | Backend Engineer & Open-Source Contributor"
template = "index.html"

[extra]
subtitle = "Backend Engineer · Open-Source Contributor"
location = "Kerala, India"
phone = "+91 88912 85207"
email = "vazthesoftwareengg@gmail.com"
github = "vasil1729"
linkedin = "vasil-abdul-razak"

hero_title = "Scalable automation platforms & real-time systems."
hero_description = "Vasil Abdul Razak is a Backend Engineer with 5+ years of experience building enterprise-grade automation platforms. As a core contributor and backend owner of Wraft—an open-source document lifecycle automation platform—he specializes in distributed systems, real-time collaboration engines, cryptographic document signing, and background workflow pipelines using Elixir/Phoenix, Go, and Rust."

metrics = [
  { val = "5+ Years", label = "building production-ready, scalable platforms" },
  { val = "120+ Stars", label = "earned on Wraft open-source repository" },
  { val = "50K+ Lines", label = "of robust production backend code authored" },
  { val = "270+ Commits", label = "driving Wraft from MVP to enterprise scale" }
]

about_title = "Architecting backend systems for real-world complexity."
about_description = "Bridging the gap between low-level performance and user-centric collaboration. Specialized in building concurrency-friendly backends, multi-tenant databases, real-time message sync, and automated compliance pipelines."
about_background_title = "Scalable architecture from day one."
about_background_p1 = "Vasil's experience extends from co-founding content-sharing platforms to architecting multi-tenant document workflows. He builds systems that carry enterprise data, handle concurrent inputs under high load, and remain reliable in mission-critical pipelines."
about_background_p2 = "At Wraft, he led the backend effort from early-stage MVP to a production-ready system capable of hosting 270+ active communities. This operational rigor extends into his freelance consulting work, delivering high-performance accounting and automation modules."

quote = "Current focus: Collaborative rich-text syncing, high-throughput background job processing, role-based access control, and cryptographic PDF workflows."

experiences = [
  { date = "Dec 2024 – Present", company = "Independent Consultant", role = "Freelance Backend Engineer", desc = "Delivering backend engineering solutions for ERP-focused systems and business automation platforms, optimizing workflows for performance and data consistency.", bullets = [
    "Developing and extending ERPNext/Frappe modules to support complex accounting workflows, reporting systems, and operational automation.",
    "Building scalable backend services and API integrations using Node.js to connect ERP systems with third-party platforms.",
    "Providing technical consultation on database schema design, queries, and performance optimization for business-critical applications."
  ] },
  { date = "Jan 2022 – Nov 2024", company = "Functionary Lab", role = "Founding Engineer / Backend Engineer", location = "Bangalore, India", desc = "Served as the core contributor and backend owner of Wraft, driving the software architecture from inception to enterprise deployment.", bullets = [
    "Designed foundational backend using Elixir/Phoenix, including role-based access control (RBAC), multi-tenant authorization, and secure data isolation.",
    "Built real-time collaborative editing engine and form builder backend using Phoenix Channels and WebSockets for conflict-free live synchronization.",
    "Architected and shipped a scalable multi-organization onboarding structure supporting 270+ active communities.",
    "Developed extensible workflow pipelines using Oban to orchestrate document approvals and complex state transitions.",
    "Implemented secure document signing and PDF processing pipelines using Elixir NIFs (Native Implemented Functions), Rust, and Java."
  ] },
  { date = "2019 – 2020", company = "Knocus Solutions PVT LTD", role = "Founding Engineer / Backend Engineer", location = "Hyderabad, India", desc = "Co-founded and drove product development for a collaborative online platform designed for creating and sharing stories, poems, and articles.", bullets = [
    "Designed and built high-performance, real-time communication systems using Go (Golang) and WebSockets.",
    "Developed robust REST APIs and managed PostgreSQL databases for dynamic content retrieval and user management."
  ] }
]

projects = [
  { title = "Wraft DLM Platform", category = "Document Lifecycle Management", desc = "An open-source document lifecycle automation system that treats documents like code—structured, version-controlled, and highly collaborative. Showcased at IndiaFOSS 2025.", bullets = [
    "Real-time collaborative editing using Phoenix Channels/WebSockets for conflict-free multi-user authoring.",
    "Extensible workflow engine built on top of Oban pipelines with granular state management.",
    "Cryptographic document signing and PDF processing utilizing high-performance Elixir NIFs and Rust."
  ], github = "https://github.com/wraft/wraft" },
  { title = "Ledger Flow Backend", category = "Multi-tenant Accounting Platform", desc = "A multi-tenant accounting platform API that bridges internal teams with external clients by proxying directly into each firm's ERPNext instance. Handles auth, task-based workflow management, financial data proxying, and push notifications through an event-driven architecture on Express 5, PostgreSQL 17, and Redis 7.", bullets = [
    "Tenant boundary modeled at the client level via a user_client_access join table, letting a single user operate across multiple client/company ERPNext instances behind one unified API.",
    "Layered architecture with seven vertical domain modules (auth, tasks, accounts, admin, dashboard, notifications, system) following a Controller → Service → Repository → Prisma flow.",
    "Custom Axios-based ERPNext/Frappe client manages cookie-session auth, getDoc/getList/rpc calls, and proactive session refresh driven by Redis keyspace notifications before TTL expiry.",
    "In-process event bus coordinates cross-cutting concerns—ERP sync from task events, audit logging, and FCM push delivery via Firebase Admin—without coupling domain modules.",
    "Defense-in-depth security: Helmet CSP/HSTS, Origin-header CSRF guard for cookie-mutating routes, Redis-backed sliding-window rate limits, jose-signed JWT access + refresh tokens, and a two-layer error classifier/formatter that redacts internals in production.",
    "Strict ESM TypeScript with Zod-validated env and request schemas, Pino structured logs with PII redaction, Prometheus metrics, and a readiness probe gated on Redis + Postgres + ERP session subscriber boot."
  ] }
]

side_projects = [
  { title = "LocalTube Audio", category = "Android · Rust + Dioxus", desc = "A local-first Android app that turns any YouTube URL into a 320 kbps MP3 with embedded album art. No backend, no ads, no tracking—everything runs on device.", stack = ["Rust", "Dioxus", "JNI", "NewPipe Extractor", "FFmpegKit", "Kotlin", "Gradle 9", "Material You"], bullets = [
    "Rust UI compiled with Dioxus and cross-compiled to aarch64-linux-android, packaged into a single APK.",
    "Calls into NewPipe Extractor (Java) and FFmpegKit (native) over JNI via the `jni` crate, with Kotlin injection bridging the Android lifecycle.",
    "Persistent download queue with animated progress and a dark Material You UI."
  ] },
  { title = "EPUB Reader", category = "Android · Flutter", desc = "A production-grade EPUB 2/3 reader with a full library, dual reading modes, and fully offline translation across 57 languages including Persian, Urdu, Arabic, and Hindi.", stack = ["Flutter", "Dart", "Google ML Kit", "CSS Columns", "SQLite"], bullets = [
    "Library with auto-scan, grid/list views, cover thumbnails, sorting, and per-chapter persistent reading position.",
    "Reader supports continuous-scroll and CSS-column paged modes, 13 themes (Solarized, Gruvbox, Dracula, Tokyo Night…), and full font/size/family controls.",
    "On-device ML Kit translation with RTL rendering, per-chapter translation cache, and an original ↔ translated toggle.",
    "Selection action bar with Copy and a conditional “Ask ChatGPT” action that appears only when the ChatGPT app is installed."
  ] }
]

recognition = [
  { title = "Wraft Featured at IndiaFOSS 2025", desc = "Showcased as an emerging open-source document automation platform at India’s premier FOSS conference, demonstrating community adoption." },
  { title = "B.Tech in Electronics & Communication", desc = "Indian Institute of Information Technology, Sri City (2014 – 2018)." }
]

skills = [
  { category = "Languages", tags = ["Elixir", "Go (Golang)", "Rust", "Python", "Java", "C/C++", "JavaScript"] },
  { category = "Backend & Databases", tags = ["Phoenix", "Ecto", "Oban", "Node.js", "PostgreSQL", "Redis", "Valkey"] },
  { category = "DevOps & Tools", tags = ["Kubernetes", "Docker", "GitHub Actions", "GitLab CI/CD", "WebSockets", "Pandoc", "LaTeX"] }
]
+++
