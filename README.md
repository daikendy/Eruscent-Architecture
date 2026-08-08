<div align="center">

# ⚡ ERUSCENT — Enterprise System Architecture & Public Specification

**Institutional Peer Tutoring, Academic Telemetry & Enterprise Multi-Tenant Platform**

Designed & Engineered by **Eruscent**

[![Next.js](https://img.shields.io/badge/Next.js-16.1-black?style=for-the-badge&logo=next.js)](https://nextjs.org/)
[![Spring Boot](https://img.shields.io/badge/Spring_Boot-3.4-6DB33F?style=for-the-badge&logo=springboot&logoColor=white)](https://spring.io/projects/spring-boot)
[![PostgreSQL](https://img.shields.io/badge/PostgreSQL-16-4169E1?style=for-the-badge&logo=postgresql&logoColor=white)](https://www.postgresql.org/)
[![Java](https://img.shields.io/badge/Java-21-ED8B00?style=for-the-badge&logo=openjdk&logoColor=white)](https://www.oracle.com/java/)
[![TypeScript](https://img.shields.io/badge/TypeScript-5.0-3178C6?style=for-the-badge&logo=typescript&logoColor=white)](https://www.typescriptlang.org/)
[![Tailwind CSS](https://img.shields.io/badge/Tailwind_CSS-v4-06B6D4?style=for-the-badge&logo=tailwindcss&logoColor=white)](https://tailwindcss.com/)
[![OWASP Hardened](https://img.shields.io/badge/OWASP-Hardened_Top_10-green?style=for-the-badge&logo=shield)](https://owasp.org/)

A production-grade, multi-tenant B2B SaaS platform connecting university students with peer tutors. Engineered with strict data isolation, dual session modes (1:1 & Group Lobbies), real-time academic telemetry, automated background maintenance, tamper-evident audit pipelines, and an OWASP-hardened security architecture.

**[🚀 Live Platform Demo](https://strive-chi-nine.vercel.app/)**

</div>

---

## 📌 1. Executive Summary & Enterprise System Architecture

**ERUSCENT** is an institutional peer tutoring and academic telemetry platform designed to bridge higher-education institutions with their academic communities (students, tutors, department heads, and platform administrators).

```
   ┌─────────────────────────────────────────────────────────────────┐
   │                        ERUSCENT TENANT HUD                      │
   │  ┌───────────────────────────────────────────────────────────┐  │
   │  │                       UNIVERSITY                          │  │
   │  └─────────────────────────────┬─────────────────────────────┘  │
   │                                │                                │
   │  ┌─────────────────────────────┴─────────────────────────────┐  │
   │  │                         CAMPUS                            │  │
   │  └─────────────────────────────┬─────────────────────────────┘  │
   │                                │                                │
   │  ┌─────────────────────────────┴─────────────────────────────┐  │
   │  │                       DEPARTMENT                          │  │
   │  └──────────────┬─────────────────────────────┬──────────────┘  │
   │                 │                             │                 │
   │  ┌──────────────┴───────────┐   ┌─────────────┴───────────┐     │
   │  │    STUDENT PRINCIPAL     │   │     TUTOR PRINCIPAL     │     │
   │  └──────────────────────────┘   └─────────────────────────┘     │
   └─────────────────────────────────────────────────────────────────┘
```

### Core Architectural Pillars

1. **Hierarchical Multi-Tenancy**: Tenant boundaries (`University` ➔ `Campus` ➔ `Department` ➔ `User`) enforced at both database and service layers with repository-level tenant scoping.
2. **Decoupled Identity & JIT Provisioning**: Authentication is offloaded to a stateless JWT/JWKS identity provider (Clerk) with Just-In-Time (JIT) user auto-provisioning and self-healing identity synchronization.
3. **Automated Maintenance & Watchdog Engines**: Scheduled background workers automate session state transitions, expired time slot purges, audit log retention, and low-attendance watchdog alerts.
4. **Tamper-Evident Security & Audit Pipeline**: Asynchronous audit logging backed by PII scrubbing, XSS/CRLF sanitization, and cryptographic HMAC-SHA256 digital signatures.
5. **Zero-Trust Domain Gating**: Institutional registration is restricted in real time via a Super-Admin-managed, database-backed domain allowlist (e.g., `@dlsu.edu.ph`, `@admu.edu.ph`).

---

## 🏗️ 2. High-Level System Architecture Diagram

```mermaid
flowchart TB
    subgraph ClientLayer ["Client & Edge Layer (Next.js 16 App Router)"]
        UI_Student["🎓 Student Marketplace & Dashboard"]
        UI_Tutor["🧑‍🏫 Tutor Management & Analytics"]
        UI_Admin["🛡️ Department Admin Portal"]
        UI_Super["👑 Super Admin Telemetry HUD"]
        Edge_CORS["🌐 Edge Gateway / CORS Security Guard"]
    end

    subgraph AuthLayer ["Identity & JWKS Provider"]
        Clerk_IdP["🔐 Clerk Identity Provider"]
        JWKS_Uri["🔑 Public JWKS Keys Endpoint"]
    end

    subgraph BackendLayer ["Backend Core — Spring Boot 3 Engine"]
        Sec_Filter["🛡️ Spring Security Filter Chain"]
        Rate_Limiter["⚡ Bucket4j Rate Limiting Interceptor"]
        Jwt_Decoder["jwtDecoder (NimbusJWKSet)"]
        JIT_Engine["🔄 JIT User Sync & Identity Healing"]
        
        subgraph Controllers ["REST API Domain Controllers"]
            Ctrl_Auth["Auth & Domain Gating"]
            Ctrl_Session["1:1 & Group Session Lobbies"]
            Ctrl_Analytics["Tutor & Dept Analytics"]
            Ctrl_Admin["Super Admin & Telemetry HUD"]
            Ctrl_Webhook["Svix Webhook Listener"]
        end

        subgraph BackgroundWorkers ["Background Execution Engine"]
            Audit_Pool["🪵 auditExecutor (2 Core / 5 Max / 100 Queue)"]
            Task_Pool["📧 taskExecutor (5 Core / 10 Max / 500 Queue)"]
            Nightly_Cron["⏰ DatabaseCleanupService (Daily @ 2:00 AM)"]
            Ghost_Watchdog["🤖 GroupSessionScheduler (Hourly Radar)"]
        end
    end

    subgraph DataLayer ["Persistence & External Services"]
        DB_Postgres[("🐘 PostgreSQL 16 (Flyway Versioned Migrations)")]
        Media_Cloudinary["☁️ Cloudinary Asset CDN"]
        Mail_Provider["📨 SMTP / JavaMailSender (Mailtrap / Production Provider)"]
    end

    ClientLayer -->|HTTPS / Bearer JWT| Edge_CORS
    Edge_CORS --> Rate_Limiter
    Rate_Limiter --> Sec_Filter
    Sec_Filter --> Jwt_Decoder
    Jwt_Decoder -.->|Stateless Public Key Fetch| JWKS_Uri
    Sec_Filter --> JIT_Engine
    JIT_Engine --> Controllers

    Controllers -->|Spring Data JPA| DB_Postgres
    Controllers -->|Async Events| BackgroundWorkers
    Audit_Pool -->|Persist HMAC Signed Logs| DB_Postgres
    Task_Pool -->|Send Transactional Emails| Mail_Provider
    Nightly_Cron -->|Purge & Auto-Complete| DB_Postgres
    Ghost_Watchdog -->|Low Attendance Alert| Mail_Provider
    Controllers -->|Profile Image Uploads| Media_Cloudinary
    Clerk_IdP -->|Svix Signed Webhooks| Ctrl_Webhook
```

---

## 🔐 3. Decoupled Identity, JWKS & JIT User Provisioning

Eruscent decouples identity authentication from application authorization by leveraging stateless JWT tokens verified against remote JWKS public keys.

```
Incoming Request (Bearer JWT)
         │
         ▼
[ JwtDecoder (NimbusJwtDecoder with JwkSetUri) ]
         │
         ▼
[ Extract Clerk Principal ID (jwt.getSubject()) ]
         │
         ├──► [ User Found in DB ] ────► Identity Healing (Sync Name & Profile Picture)
         │                                       │
         └──► [ User Not Found ] ────► Just-In-Time (JIT) Auto-Provisioning
                                                 │
                                                 ▼
                             [ Map Granted Authorities & Dual Roles ]
                             (ROLE_STUDENT, ROLE_TUTOR, ROLE_ADMIN)
```

### Identity Architecture Features

* **Stateless Token Verification**: Authentication overhead is minimized by verifying incoming JWT signatures against cached JWKS endpoints (`spring.security.oauth2.resourceserver.jwt.jwk-set-uri`).
* **Just-In-Time (JIT) Provisioning**: If a user authenticates via Clerk but does not yet exist in the local PostgreSQL database, `userService.createEmptyUserFromClerk()` auto-provisions their initial account context.
* **Identity Self-Healing**: On each request, if a user's full name or profile picture URL in the JWT claims differs from the database record, the backend automatically updates and heals the local entity.
* **Dual Role Aggregation**: Supports multi-role principals (e.g., a student who is also an approved tutor) by mapping all active roles into the Spring Security Context (`CustomJwtAuthenticationToken`).

---

## ⚡ 4. High-Concurrency Asynchronous & Scheduled Engine

Eruscent combines dedicated thread pools with automated background schedulers to guarantee high throughput and clean data maintenance.

```
                        ┌──────────────────────────────────────────┐
                        │      SPRING @ENABLEASYNC THREAD POOLS    │
                        └────────────────────┬─────────────────────┘
                                             │
                       ┌─────────────────────┴─────────────────────┐
                       ▼                                           ▼
          [ auditExecutor Thread Pool ]               [ taskExecutor Thread Pool ]
          • Core Threads: 2                           • Core Threads: 5
          • Max Threads: 5                            • Max Threads: 10
          • Queue Capacity: 100                       • Queue Capacity: 500
          • Isolates HMAC Audit Logging               • Handles Email Notifications
```

### Automated Background Schedulers

1. **Nightly Database Maintenance (`DatabaseCleanupService`)**:
   * Runs daily at 2:00 AM (`@Scheduled(cron = "0 0 2 * * *")`).
   * **Slot Purging**: Deletes all past, unbooked `TimeSlot` entities.
   * **1:1 Session Auto-Completion**: Transitions past confirmed 1-on-1 tutoring sessions to `COMPLETED` after a 24-hour grace period.
   * **Group Session Auto-Completion**: Completes populated group classes 24 hours post-schedule.
   * **Empty Group Cancellation**: Cancels unpopulated group sessions automatically.
   * **Audit Log Retention Pruning**: Deletes audit logs older than 365 days.
2. **Pending Session Auto-Expiry**:
   * Runs every 15 minutes (`@Scheduled(cron = "0 0/15 * * * *")`).
   * Auto-expires pending session requests that tutors failed to accept or reject before their scheduled start time.
3. **Ghost-Town Low Attendance Watchdog (`GroupSessionScheduler`)**:
   * Runs hourly (`@Scheduled(cron = "0 0 * * * *")`).
   * Scans for group sessions starting in the next 12 hours with fewer than 3 enrolled students.
   * Dispatches warning emails to tutors so they can decide whether to proceed or cancel.

---

## 🔒 5. OWASP-Hardened Security & Cryptographic Audit Pipeline

Eruscent was subjected to a comprehensive security engineering audit, implementing multi-layered controls against OWASP Top 10 vulnerabilities.

```
       ┌─────────────────────────────────────────────────────────────┐
       │                   AUDIT EVENT GENERATED                     │
       └──────────────────────────────┬──────────────────────────────┘
                                      │
                                      ▼
       ┌─────────────────────────────────────────────────────────────┐
       │              1. PII & Secret Scrubbing                      │
       │     (Redacts Passwords, Tokens, API Keys, and Emails)       │
       └──────────────────────────────┬──────────────────────────────┘
                                      │
                                      ▼
       ┌─────────────────────────────────────────────────────────────┐
       │         2. Log Forging & XSS Sanitization                   │
       │     (CRLF Removal & HTML Escaping via HtmlUtils)            │
       └──────────────────────────────┬──────────────────────────────┘
                                      │
                                      ▼
       ┌─────────────────────────────────────────────────────────────┐
       │      3. HMAC-SHA256 Cryptographic Signature Generation      │
       │     sign(userId, action, details, timestamp, auditSecret)   │
       └──────────────────────────────┬──────────────────────────────┘
                                      │
                                      ▼
       ┌─────────────────────────────────────────────────────────────┐
       │         4. Asynchronous Database Persistence                │
       └─────────────────────────────────────────────────────────────┘
```

### Security Engineering Controls

* **Tamper-Evident Digital Signatures**: Every audit record saved via `AuditEventListener` contains an `HMAC-SHA256` signature computed over `userId|action|details|timestamp` using an immutable server key.
* **PII & Credential Scrubbing**: `AuditSecurityUtils` applies regex masking to strip passwords, secret keys, bearer tokens, and email addresses prior to log persistence.
* **Insecure Direct Object Reference (IDOR) Isolation**: Database queries for session management, time slots, and reviews enforce principal ownership checks (`WHERE s.student.id = :userId OR s.tutor.user.id = :userId`).
* **Security Response Headers**:
  * `Strict-Transport-Security` (HSTS): `max-age=31536000; includeSubDomains`
  * `X-Frame-Options`: `DENY`
  * `Referrer-Policy`: `strict-origin-when-cross-origin`
* **Zero Mass Assignment**: Incoming request payloads map exclusively to validated DTOs, prohibiting client-side entity field tampering.

---

## 🎯 6. Feature Capability & System Architecture Mapping

| Feature Capability | Functional Description | Architecture Component | Primary Security & Operational Control |
|---|---|---|---|
| **Domain-Gated Signup** | Restricts student registration to verified university email domains | `EmailDomainController` & `AllowedEmailDomain` | Super Admin managed, real-time DB allowlist check |
| **Tutor Marketplace** | Searchable directory by subject, campus, hourly rate, and rating | `TutorProfileController` & JPA Specifications | Public GET cache, active profile filtering |
| **1:1 Session Engine** | Real-time booking calendar, time slot locks, session state machine | `TutoringSessionService` | IDOR owner isolation, pending auto-expiry |
| **Group Session Lobbies**| Multi-student group sessions, capacity bounds, automated enrollment | `GroupSessionService` & `Enrollment` | Capacity checks, hourly low-attendance watchdog |
| **Tutor Analytics** | 7-day earnings yield, retention rate, daily yield analytics | `TutorAnalyticsController` | Custom SQL DTO projections, read-only isolation |
| **Department Admin Portal**| Tutor verification workflows, 30-day KPI snapshots, subject bottlenecks | `AdminController` | Department-scoped queries, `@PreAuthorize("hasRole('ADMIN')")` |
| **Super Admin HUD** | Platform-wide telemetry, system anomalies, domain allowlist manager | `SuperAdminController` & `SuperAdminTelemetryController` | Platform RBAC, zero-downtime allowlist updates |
| **Media Management** | Profile picture avatar uploads & CDN asset delivery | Cloudinary Service | Multipart size checks, rate-limited upload profile |

---

## 📊 7. Entity-Relationship & Data Model Overview

```mermaid
erDiagram
    UNIVERSITY ||--|{ CAMPUS : contains
    CAMPUS ||--|{ DEPARTMENT : contains
    DEPARTMENT ||--|{ USER : employs_or_enrolls
    USER ||--o| TUTOR_PROFILE : presents
    USER ||--o{ TUTORING_SESSION : books_as_student
    TUTOR_PROFILE ||--o{ TUTORING_SESSION : conducts_as_tutor
    TUTOR_PROFILE ||--o{ TIME_SLOT : publishes
    TUTOR_PROFILE ||--o{ GROUP_SESSION : hosts
    GROUP_SESSION ||--|{ ENROLLMENT : registers
    USER ||--o{ ENROLLMENT : enrolls_in
    TUTORING_SESSION ||--o| REVIEW : receives
    USER ||--o{ AUDIT_LOG : triggers
    UNIVERSITY ||--o{ ALLOWED_EMAIL_DOMAIN : enforces

    USER {
        bigint id PK
        string clerk_id UK
        string email UK
        string full_name
        string profile_picture_url
        enum roles
        boolean is_active
        timestamp created_at
    }

    TUTOR_PROFILE {
        bigint id PK
        bigint user_id FK
        string bio
        decimal hourly_rate
        double average_rating
        integer total_reviews
        boolean is_approved
    }

    TUTORING_SESSION {
        bigint id PK
        bigint student_id FK
        bigint tutor_profile_id FK
        timestamp start_time
        timestamp end_time
        enum status
        string notes
    }

    GROUP_SESSION {
        bigint id PK
        bigint tutor_profile_id FK
        string title
        integer max_capacity
        integer current_capacity
        boolean low_attendance_warning_sent
        enum status
    }

    AUDIT_LOG {
        bigint id PK
        string action
        string details
        string digital_signature
        timestamp created_at
    }

    ALLOWED_EMAIL_DOMAIN {
        bigint id PK
        string domain UK
        boolean is_active
    }
```

---

## 🛡️ 8. Rate Limiting & Denial-of-Service (DoS) Protection Matrix

Gateway rate limiting is managed by `RateLimitInterceptor` using **Bucket4j**:

| Rate Limit Profile | URI Patterns / Protected Endpoints | Allowance Threshold | Bucket Refill Strategy | Action on Overflow |
|---|---|---|---|---|
| **Auth & Upload Profile** | `/api/v1/auth/**`, `/api/v1/users/login`, `/api/v1/users/register`, `/upload` | **5 requests / minute** | Per-IP Token Bucket | HTTP 429 Too Many Requests |
| **Public Contact Profile** | `/api/v1/public/contact` | **2 requests / hour** | Per-IP Token Bucket | HTTP 429 Too Many Requests |
| **State Mutation Profile** | All state-modifying requests (`POST`, `PUT`, `DELETE`, `PATCH`) | **60 requests / minute** | Per-IP Token Bucket | HTTP 429 Too Many Requests |
| **Read Bypass** | All `GET` and `OPTIONS` pre-flight requests | **Unlimited / Unthrottled** | Bypass Rule | Allowed |

### Reverse-Proxy Aware IP Extraction

To prevent IP spoofing attacks via client-supplied headers, `RateLimitInterceptor` parses the `X-Forwarded-For` header chain and extracts the **last IP address** (the address appended by trusted reverse proxies such as Railway/Cloudflare) rather than trusting client-injected positions.

---

## 🪵 9. Production Structured Telemetry & Observability Pipeline

Eruscent includes structured telemetry and observability out of the box:

```json
{
  "timestamp": "2026-08-08T23:15:50.000Z",
  "level": "INFO",
  "logger": "com.strive.backend.config.SecurityConfig",
  "thread": "http-nio-8080-exec-1",
  "message": "SECURITY TELEMETRY",
  "context": {
    "clerkId": "user_2tX9kL...7mP",
    "userFound": true,
    "resolvedRoles": ["ROLE_STUDENT", "ROLE_TUTOR"],
    "mappedAuthorities": ["ROLE_STUDENT", "ROLE_TUTOR"]
  }
}
```

### Observability Features

* **Health Probes**: Spring Boot Actuator health and readiness endpoints configured at `/actuator/health`.
* **Structured Log Formatting**: SLF4J and Logback configured for structured ISO-8601 JSON log aggregation.
* **Department KPI Historical Snapshots**: 30-day historical analytics tracking session completion rates, student retention, and departmental subject bottlenecks.

---

## 📱 10. Responsive Frontend & Mobile Layout Architecture

The frontend client layer is built with a modern, high-performance web architecture:

* **Framework**: Next.js 16 (App Router) with React 19 and TypeScript 5.
* **Styling System**: Tailwind CSS v4 with dynamic dark mode (`next-themes`) and Radix UI primitives.
* **Visual FX & Icons**: Lucide React icons, Framer Motion animations, and Canvas Confetti feedback.
* **State Management**: TanStack React Query (`v5`) handling API caching, optimistic UI updates, and stale-while-revalidate policies.

---

## 🛠️ 11. Technology Stack Breakdown

| Layer | Technology | Version | Key Responsibilities |
|---|---|---|---|
| **Frontend Core** | Next.js (App Router) | `16.1.6` | Client dashboard UI, SSR, layout routing |
| **UI Library** | React | `19.2.3` | Reactive component rendering |
| **Styling** | Tailwind CSS | `v4` | Design tokens, responsive utility classes |
| **Data Fetching** | TanStack React Query | `v5.90.21` | Client-side API query caching & mutation |
| **Validation (Client)**| Zod | `v4.3.6` | Frontend form & contract validation |
| **Backend Core** | Spring Boot | `3.4.2` | Enterprise REST API engine |
| **Runtime** | Java OpenJDK | `21` | High-performance backend execution |
| **Security** | Spring Security | `3.4.2` | OAuth2 Resource Server & `@PreAuthorize` RBAC |
| **Identity Provider** | Clerk | `@clerk/nextjs` | Authentication & token issuance |
| **Webhook Verifier** | Svix | `1.90.0` | Cryptographic HMAC webhook verification |
| **Rate Limiter** | Bucket4j | `8.10.1` | Per-IP token bucket rate limiting |
| **Database** | PostgreSQL | `16` | Relational data persistence |
| **Migrations** | Flyway | Built-in | Database versioning & automated migrations |
| **Media CDN** | Cloudinary | API v2 | Profile avatar & media asset storage |
| **Email Service** | JavaMailSender | Spring Starter | Asynchronous transactional notification mail |

---

## 🗺️ 12. High-Level API Domain Map

All API endpoints are exposed under the `/api/v1` namespace:

| Group | Base Path | Required Access / Role | Rate Limit Profile | Purpose |
|---|---|---|---|---|
| **Auth** | `/api/v1/auth/**` | Public / Authenticated | Auth Profile (5 req/min) | Identity synchronization & session context |
| **Users** | `/api/v1/users/**` | Authenticated / Self | Auth Profile (sensitive routes) | User profiles & avatar updates |
| **Sessions (1:1)** | `/api/v1/sessions/**` | `ROLE_STUDENT`, `ROLE_TUTOR` | Standard Profile (60 req/min) | 1-on-1 session booking state machine |
| **Group Lobbies** | `/api/v1/lobbies/**` | `ROLE_STUDENT`, `ROLE_TUTOR` | Standard Profile (60 req/min) | Group session creation & auto-enrollment |
| **Availability** | `/api/v1/timeslots/**` | `ROLE_TUTOR` | Standard Profile (60 req/min) | Tutor calendar time slot publishing |
| **Tutor Profiles** | `/api/v1/profiles/**` | Public / Authenticated | Read Bypass (GET) | Public tutor directory search |
| **Dashboard** | `/api/v1/dashboards/**` | Student, Tutor, Admin | Standard Profile (60 req/min) | Role-based aggregate dashboards |
| **Analytics** | `/api/v1/tutor/analytics` | `ROLE_TUTOR` | Standard Profile (60 req/min) | Tutor earnings yield & retention analytics |
| **Admin** | `/api/v1/admin/**` | `ROLE_ADMIN` | Standard Profile (60 req/min) | Tutor approval & department KPIs |
| **Super Admin** | `/api/v1/super/**` | `ROLE_SUPER_ADMIN` | Standard Profile (60 req/min) | Platform administration & domain allowlist |
| **Universities** | `/api/v1/universities/**` | Public | Read Bypass (GET) | Institutional campus lookup |

---

## 💡 13. Architecture Strategy: Public Spec & Private Implementation

Designed by **Eruscent**, this project adopts an **"Open Architecture Specification, Private Source Code Implementation"** repository model.

```
       ┌─────────────────────────────────────────────────────────────────┐
       │                PUBLIC SPECIFICATION REPOSITORY                  │
       │                   (GitHub: Public Repository)                   │
       │  • Architectural Blueprints & System Design Flowcharts          │
       │  • OpenAPI 3.0 Route Contracts & Domain Mapping                 │
       │  • Entity-Relationship Diagrams (ERD)                           │
       │  • Security Audit Controls & Rate Limiting Matrices             │
       └────────────────────────────────┬────────────────────────────────┘
                                        │
                                        ▼
       ┌─────────────────────────────────────────────────────────────────┐
       │             PRIVATE IMPLEMENTATION SOURCE CODE BASE             │
       │                  (GitHub: Private Repository)                   │
       │  • Proprietary Java 21 / Spring Boot 3 Engine                   │
       │  • Next.js 16 App Router Codebase                               │
       │  • Production Database Migrations & Environment Credentials     │
       └─────────────────────────────────────────────────────────────────┘
```

### Strategic Benefits

1. **Intellectual Property Protection**: Proprietary business logic, database migrations, and backend code stay protected in private repositories.
2. **Public System Design Showcase**: Technical stakeholders and potential enterprise clients can inspect **Eruscent's** software architecture, security practices, and engineering standards.
3. **Clean Contract Interfaces**: Integration partners and frontend developers can build against explicit interface specs without needing access to underlying private repositories.

---

<div align="center">

**Designed & Architected by Eruscent**  
*Building Secure, Scalable, and Modern Enterprise Systems.*

</div>
