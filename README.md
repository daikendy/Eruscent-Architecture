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
[![Flyway Migrations](https://img.shields.io/badge/Flyway-PostgreSQL_v16-CC0200?style=for-the-badge&logo=flyway&logoColor=white)](https://flywaydb.org/)
[![GitHub Actions CI/CD](https://img.shields.io/badge/GitHub_Actions-CI%2FCD_Pipeline-2088FF?style=for-the-badge&logo=githubactions&logoColor=white)](https://github.com/features/actions)
[![OpenAPI 3.0](https://img.shields.io/badge/OpenAPI-3.0_Swagger-85EA2D?style=for-the-badge&logo=openapi-initiative&logoColor=black)](https://swagger.io/)
[![OWASP Hardened](https://img.shields.io/badge/OWASP-Hardened_Top_10-green?style=for-the-badge&logo=shield)](https://owasp.org/)

A production-grade, multi-tenant B2B SaaS platform connecting university students with peer tutors. Engineered with strict data isolation, dual session modes (1:1 & Group Lobbies), real-time academic telemetry, dynamic JPA Criteria specifications, zero-trust peer messaging, verified review aggregation, in-memory query caching, optimistic concurrency locking, automated background maintenance, timezone-aware gamification streaks, tamper-evident audit pipelines, resilient client retry interceptors, interactive OpenAPI docs, automated containerized CI/CD testing, and an OWASP-hardened security architecture.

**[🚀 Live Platform Demo](https://www.eruscent.com/)**

</div>

---

## 📋 Table of Contents

<br/>

### **PART I: EXECUTIVE OVERVIEW & SYSTEM BLUEPRINTS**

* 📌 [**1. Executive Summary & Core Multi-Tenant Architecture**](#-1-executive-summary--core-multi-tenant-architecture)
* 🏗️ [**2. High-Level System Architecture Diagram**](#%EF%B8%8F-2-high-level-system-architecture-diagram)
* 💡 [**3. Architecture Strategy: Public Spec & Private Implementation**](#-3-architecture-strategy-public-spec--private-implementation)
<br/>

### **PART II: CORE ENGINE PILLARS (THE HEAVYWEIGHT FEATURES)**

* 🔐 [**4. Decoupled Identity, JWKS & JIT User Provisioning**](#-4-decoupled-identity-jwks--jit-user-provisioning)
* 🌐 [**5. Dynamic Institutional Domain Gating & Allowlist Engine**](#-5-dynamic-institutional-domain-gating--allowlist-engine)
* 📅 [**6. Dual Session Architecture & Schedule Conflict Engine**](#-6-dual-session-architecture--schedule-conflict-engine)
* ⚡ [**7. Concurrency Safety & Optimistic Locking Guard**](#-7-concurrency-safety--optimistic-locking-guard)
* 🔎 [**8. Dynamic JPA Criteria API Search & Filtering Engine**](#-8-dynamic-jpa-criteria-api-search--filtering-engine)
* 💬 [**9. Zero-Trust In-Session Peer Chat & Notification Radar**](#-9-zero-trust-in-session-peer-chat--notification-radar)
* ⭐ [**10. Verified Session Review & Math-Rounded Rating Engine**](#-10-verified-session-review--math-rounded-rating-engine)
* 🔥 [**11. Timezone-Aware Gamification & Activity Streak Engine**](#-11-timezone-aware-gamification--activity-streak-engine)
<br/>

### **PART III: SECURITY, RESILIENCE & EXCEPTION CONTRACTS**

* 🔒 [**12. OWASP-Hardened Security & Multi-Subdomain CORS Matrix**](#-12-owasp-hardened-security--multi-subdomain-cors-matrix)
* 🛡️ [**13. Rate Limiting & Denial-of-Service (DoS) Protection Matrix**](#%EF%B8%8F-13-rate-limiting--denial-of-service-dos-protection-matrix)
* 🔄 [**14. Resilient Client Interceptor & Automatic Retry Engine**](#-14-resilient-client-interceptor--automatic-retry-engine)
* 📐 [**15. Uniform Enterprise Exception Contract & ISO-8601 Serialization**](#-15-uniform-enterprise-exception-contract--iso-8601-serialization)
<br/>

### **PART IV: TELEMETRY, PERFORMANCE & BACKGROUND ENGINES**

* ⚙️ [**16. High-Concurrency Asynchronous & Scheduled Engine**](#%EF%B8%8F-16-high-concurrency-asynchronous--scheduled-engine)
* 🚀 [**17. In-Memory Telemetry & Treemap Caching Engine (`@Cacheable`)**](#-17-in-memory-telemetry--treemap-caching-engine-cacheable)
* 📈 [**18. Institutional Analytics & Departmental Bottleneck Telemetry**](#-18-institutional-analytics--departmental-bottleneck-telemetry)
* 🪵 [**19. Production Structured Telemetry & Observability Pipeline**](#-19-production-structured-telemetry--observability-pipeline)
<br/>

### **PART V: DEVOPS, SCHEMA & REFERENCE SCHEMAS**

* 🛠️ [**20. Automated CI/CD Pipeline & Full-Stack DevOps Architecture**](#%EF%B8%8F-20-automated-cicd-pipeline--full-stack-devops-architecture)
* 🏗️ [**21. Environment Profile Isolation & 12-Factor Production Tiering**](#%EF%B8%8F-21-environment-profile-isolation--12-factor-production-tiering)
* 🐘 [**22. Versioned Schema Evolution & Automated Seeder Engine**](#-22-versioned-schema-evolution--automated-seeder-engine)
* 📖 [**23. OpenAPI 3.0 & Interactive Swagger UI Pipeline**](#-23-openapi-30--interactive-swagger-ui-pipeline)
* 📊 [**24. Entity-Relationship & Data Model Overview**](#-24-entity-relationship--data-model-overview)
* 🎯 [**25. Feature Capability & System Architecture Mapping**](#-25-feature-capability--system-architecture-mapping)
* 🗺️ [**26. High-Level API Domain Map**](#%EF%B8%8F-26-high-level-api-domain-map)
* 📱 [**27. Responsive Frontend & Mobile Layout Architecture**](#-27-responsive-frontend--mobile-layout-architecture)
* 🛠️ [**28. Technology Stack Breakdown**](#%EF%B8%8F-28-technology-stack-breakdown)

<br/>

---

# PART I: EXECUTIVE OVERVIEW & SYSTEM BLUEPRINTS

## 📌 1. Executive Summary & Core Multi-Tenant Architecture

**ERUSCENT** is an institutional peer tutoring and academic telemetry platform designed to bridge higher-education institutions with their academic communities (students, tutors, department heads, and platform administrators).

```mermaid
flowchart TD
    subgraph HUD ["🏛️ ERUSCENT MULTI-TENANT INSTITUTIONAL HIERARCHY"]
        direction TD
        U["🏫 UNIVERSITIES (Tenant Root Isolation)"]
        C["🏬 CAMPUSES (Domain-Locked Operations)"]
        D["🔬 DEPARTMENTS (Academic Scoping & Telemetry)"]
        
        subgraph Principals ["👥 USER PRINCIPALS"]
            S["🎓 STUDENT PRINCIPALS"]
            T["🧑‍🏫 TUTOR PRINCIPALS"]
        end
    end

    U --> C
    C --> D
    D --> S
    D --> T

    classDef univ fill:#1e1b4b,stroke:#818cf8,stroke-width:2px,color:#ffffff;
    classDef campus fill:#0f172a,stroke:#38bdf8,stroke-width:2px,color:#ffffff;
    classDef dept fill:#064e3b,stroke:#34d399,stroke-width:2px,color:#ffffff;
    classDef user fill:#701a75,stroke:#f0abfc,stroke-width:2px,color:#ffffff;

    class U univ;
    class C campus;
    class D dept;
    class S,T user;
```

### Core Architectural Pillars

1. **Hierarchical Multi-Tenancy**: Tenant boundaries (`University` ➔ `Campus` ➔ `Department` ➔ `User`) enforced at both database and service layers with repository-level tenant scoping.
2. **Decoupled Identity & JIT Provisioning**: Authentication is offloaded to a stateless JWT/JWKS identity provider (Clerk) with Just-In-Time (JIT) user auto-provisioning and self-healing identity synchronization.
3. **Dynamic Institutional Domain Gating**: Registration is restricted in real time via a Super-Admin-managed, 3-tier domain allowlist engine (`EmailDomainService`).
4. **Dual Session & Conflict Engine**: Supports 1-on-1 bookings and multi-student group lobbies with real-time schedule conflict prevention and capacity locks.
5. **Optimistic Concurrency Control**: JPA optimistic locking (`ObjectOptimisticLockingFailureException`) prevents race conditions during high-volume simultaneous bookings.
6. **Dynamic JPA Specification Search**: Multi-field search across tutor names, bios, and course codes using Spring Data JPA Criteria API with distinct deduplication.
7. **Zero-Trust Peer Chat Radar**: In-session chat access control (`validateUserAccess`) with dynamic enrollment revocation and batch notification queries.
8. **Verified Review Aggregation**: Rating engine permitting reviews strictly for completed sessions, preventing self-reviews, and auto-calculating rounded average ratings.
9. **In-Memory Telemetry Caching**: Spring `@Cacheable` abstraction caching global KPIs and university heatmap node trees to eliminate DB load during high-traffic admin reloads.
10. **Timezone-Aware Gamification**: Automated activity streak calculation (`updateStreak`) maintaining student and tutor engagement across international timezones.
11. **Resilient Client Interceptor**: Next.js client-side Axios layer featuring automatic exponential backoff retries for transient HTTP errors (502-504, 429, timeouts).
12. **Automated CI/CD & Security Workflows**: GitHub Actions integration pipelines featuring live PostgreSQL 16 service containers and automated weekly security dependency audits.
13. **Automated Maintenance & Watchdogs**: Scheduled background workers automate session state transitions, expired time slot purges, audit log retention, and low-attendance alerts.
14. **Tamper-Evident Security & Audit Pipeline**: Asynchronous audit logging backed by PII scrubbing, XSS/CRLF sanitization, and cryptographic HMAC-SHA256 digital signatures.

---

## 🏗️ 2. High-Level System Architecture Diagram

```mermaid
flowchart TB
    subgraph ClientLayer ["📱 Client Layer (Next.js 16 App Router)"]
        UI_Student["🎓 Student Marketplace & Dashboard"]
        UI_Tutor["🧑‍🏫 Tutor Management & Analytics"]
        UI_Admin["🛡️ Department Admin Portal"]
        UI_Super["👑 Super Admin Telemetry HUD"]
        Axios_Client["⚡ Resilient Axios Client (Retry Interceptor)"]
    end

    subgraph AuthLayer ["🔐 Identity & JWKS Provider"]
        Clerk_IdP["🔐 Clerk Identity Provider & Avatar CDN"]
        JWKS_Uri["🔑 Public JWKS Keys Endpoint"]
    end

    subgraph BackendLayer ["⚙️ Backend Core — Spring Boot 3 Engine"]
        Sec_Filter["🛡️ Spring Security Filter Chain"]
        Rate_Limiter["⚡ Bucket4j Rate Limiting Interceptor"]
        Jwt_Decoder["jwtDecoder (NimbusJWKSet)"]
        JIT_Engine["🔄 JIT User Sync & Identity Healing"]
        Domain_Guard["🌐 EmailDomainService (3-Tier Gating)"]
        Cache_Manager["🚀 Spring @Cacheable Layer"]
        
        subgraph Controllers ["REST API Domain Controllers"]
            Ctrl_Auth["Auth & Domain Gating"]
            Ctrl_Session["1:1 & Group Session Lobbies"]
            Ctrl_Analytics["Tutor & Dept Analytics"]
            Ctrl_Chat["💬 MessageController (Peer Chat)"]
            Ctrl_Review["⭐ ReviewController (Verified Ratings)"]
            Ctrl_Admin["Super Admin & Telemetry HUD"]
            Ctrl_Webhook["Svix Webhook Listener"]
            Ctrl_OpenAPI["📖 OpenAPI 3.0 Swagger UI"]
        end

        subgraph ExceptionLayer ["Enterprise Error & Concurrency Guard"]
            Global_Handler["📐 GlobalExceptionHandler (RFC 7807 Error Contract)"]
            Opt_Locking["⚡ JPA Optimistic Locking Guard"]
        end

        subgraph Engines ["Core Business Engines"]
            Conflict_Engine["📅 Overlap Conflict Resolver"]
            Search_Engine["🔎 Dynamic JPA Specification Engine"]
            Streak_Engine["🔥 Timezone-Aware Streak Engine"]
            Rating_Engine["⭐ Math-Rounded Review Aggregator"]
        end

        subgraph BackgroundWorkers ["Background Execution Engine"]
            Audit_Pool["🪵 auditExecutor Pool"]
            Task_Pool["📧 taskExecutor Pool"]
            Nightly_Cron["⏰ DatabaseCleanupService"]
            Ghost_Watchdog["🤖 GroupSessionScheduler"]
        end
    end

    subgraph DevOpsLayer ["🛠️ DevOps & Automated CI/CD"]
        GHA_CI["🛠️ GitHub Actions (Java 21 + Live Postgres 16 Container)"]
        GHA_Audit["🛡️ Weekly Dependency Security Audit Cron"]
    end

    subgraph DataLayer ["🐘 Persistence & External Services"]
        DB_Postgres[("🐘 PostgreSQL 16 (Flyway Migrations)")]
        Mail_Provider["📨 SMTP / JavaMailSender"]
    end

    ClientLayer --> Axios_Client
    Axios_Client -->|HTTPS / Bearer JWT| Rate_Limiter
    Rate_Limiter --> Sec_Filter
    Sec_Filter --> Jwt_Decoder
    Jwt_Decoder -.->|Stateless Public Key Fetch| JWKS_Uri
    Sec_Filter --> JIT_Engine
    JIT_Engine --> Domain_Guard
    Domain_Guard --> Controllers

    Controllers --> Cache_Manager
    Cache_Manager --> ExceptionLayer
    ExceptionLayer --> Engines
    Engines -->|Spring Data JPA| DB_Postgres
    Controllers -->|Async Events| BackgroundWorkers
    Audit_Pool -->|Persist HMAC Signed Logs| DB_Postgres
    Task_Pool -->|Send Transactional Emails| Mail_Provider
    Nightly_Cron -->|Purge & Auto-Complete| DB_Postgres
    Ghost_Watchdog -->|Low Attendance Alert| Mail_Provider
    Clerk_IdP -->|Svix Signed Webhooks| Ctrl_Webhook

    GHA_CI -.->|Automated Integration Build| BackendLayer
    GHA_Audit -.->|Automated Vulnerability Scanner| ClientLayer

    classDef client fill:#0369a1,stroke:#38bdf8,stroke-width:2px,color:#ffffff;
    classDef auth fill:#581c87,stroke:#c084fc,stroke-width:2px,color:#ffffff;
    classDef backend fill:#065f46,stroke:#34d399,stroke-width:2px,color:#ffffff;
    classDef devops fill:#9a3412,stroke:#fb923c,stroke-width:2px,color:#ffffff;
    classDef data fill:#1e3a8a,stroke:#60a5fa,stroke-width:2px,color:#ffffff;

    class UI_Student,UI_Tutor,UI_Admin,UI_Super,Axios_Client client;
    class Clerk_IdP,JWKS_Uri auth;
    class Sec_Filter,Rate_Limiter,Jwt_Decoder,JIT_Engine,Domain_Guard,Cache_Manager backend;
    class GHA_CI,GHA_Audit devops;
    class DB_Postgres,Mail_Provider data;
```

---

## 💡 3. Architecture Strategy: Public Spec & Private Implementation

Designed by **Eruscent**, this project adopts an **"Open Architecture Specification, Private Source Code Implementation"** repository model.

```mermaid
flowchart TD
    subgraph PublicRepo ["🌐 PUBLIC SPECIFICATION REPOSITORY (GitHub Public)"]
        P1["• Architectural Blueprints & Flowcharts"]
        P2["• OpenAPI 3.0 Route Contracts & Domain Maps"]
        P3["• Entity-Relationship Diagrams (ERD)"]
        P4["• Security Audit Controls & Rate Limiting Matrices"]
    end

    subgraph PrivateRepo ["🔒 PRIVATE IMPLEMENTATION REPOSITORY (GitHub Private)"]
        R1["• Proprietary Java 21 / Spring Boot 3 Core Engine"]
        R2["• Next.js 16 App Router Frontend Codebase"]
        R3["• Production Flyway Migrations & Cloud Credentials"]
    end

    PublicRepo ==>|Defines System Architecture Contract| PrivateRepo

    classDef pub fill:#1e293b,stroke:#38bdf8,stroke-width:2px,color:#ffffff;
    classDef priv fill:#0f172a,stroke:#a855f7,stroke-width:2px,color:#ffffff;

    class P1,P2,P3,P4 pub;
    class R1,R2,R3 priv;
```

---

# PART II: CORE ENGINE PILLARS (THE HEAVYWEIGHT FEATURES)

## 🔐 4. Decoupled Identity, JWKS & JIT User Provisioning

Eruscent decouples identity authentication from application authorization by leveraging stateless JWT tokens verified against remote JWKS public keys.

```mermaid
flowchart TD
    A["Incoming Request (Bearer JWT)"] --> B["JwtDecoder (NimbusJwtDecoder with JwkSetUri)"]
    B --> C["Extract Clerk Principal ID (jwt.getSubject())"]
    C --> D{"User Found in DB?"}
    
    D -- "YES" --> E["Identity Self-Healing (Sync Name & Profile Picture)"]
    D -- "NO" --> F["Just-In-Time (JIT) Auto-Provisioning"]
    
    E --> G["Map Granted Authorities & Dual Roles (ROLE_STUDENT, ROLE_TUTOR, ROLE_ADMIN)"]
    F --> G

    classDef step fill:#1e1b4b,stroke:#818cf8,stroke-width:2px,color:#ffffff;
    classDef pass fill:#064e3b,stroke:#34d399,stroke-width:2px,color:#ffffff;
    classDef act fill:#701a75,stroke:#f0abfc,stroke-width:2px,color:#ffffff;

    class A,B,C,D step;
    class E,G pass;
    class F act;
```

### Identity Architecture Features

* **Stateless Token Verification**: Authentication overhead is minimized by verifying incoming JWT signatures against cached JWKS endpoints (`spring.security.oauth2.resourceserver.jwt.jwk-set-uri`).
* **Just-In-Time (JIT) Provisioning**: If a user authenticates via Clerk but does not yet exist in the local PostgreSQL database, `userService.createEmptyUserFromClerk()` auto-provisions their initial account context.
* **Identity Self-Healing**: On each request, if a user's full name or profile picture URL in the JWT claims differs from the database record, the backend automatically updates and heals the local entity.
* **Dual Role Aggregation**: Supports multi-role principals (e.g., a student who is also an approved tutor) by mapping all active roles into the Spring Security Context (`CustomJwtAuthenticationToken`).

---

## 🌐 5. Dynamic Institutional Domain Gating & Allowlist Engine

To maintain strict institutional boundaries, Eruscent incorporates a **3-tier domain validation strategy** managed by `EmailDomainService`:

```mermaid
flowchart TD
    A["User Registration Request (email)"] --> B["1. Check Authoritative DB Table (allowed_email_domains)"]
    B --> C{"Active DB Domains Exist?"}
    
    C -- "YES" --> D["Match Email Domain against DB Entries"]
    D -- "Match" --> E["✅ Allow Registration"]
    D -- "No Match" --> F["❌ Block Registration"]
    
    C -- "NO (Bootstrap)" --> G["2. Fallback to Env Property (app.registration.allowed-domains)"]
    G -- "Env Set & Match" --> E
    G -- "Env Blank / Unconfigured" --> H["3. Default Fallback: DENY ALL"]

    classDef check fill:#0f172a,stroke:#38bdf8,stroke-width:2px,color:#ffffff;
    classDef ok fill:#064e3b,stroke:#34d399,stroke-width:2px,color:#ffffff;
    classDef deny fill:#881337,stroke:#f43f5e,stroke-width:2px,color:#ffffff;

    class A,B,C,D,G check;
    class E ok;
    class F,H deny;
```

---

## 📅 6. Dual Session Architecture & Schedule Conflict Engine

Eruscent implements two distinct tutoring session modes with real-time schedule conflict resolution:

```mermaid
flowchart TD
    Root["🗓️ DUAL TUTORING SESSION ARCHITECTURE"]
    Root --> M1["1-on-1 Private Sessions"]
    Root --> M2["Group Session Lobbies"]

    M1 --> F1["• Calendar time slot booking"]
    M1 --> F2["• Direct tutor acceptance / rejection"]
    M1 --> F3["• Single student reservation"]
    M1 --> F4["• Pending auto-expiry (15 mins)"]

    M2 --> G1["• Multi-student group lobby"]
    M2 --> G2["• Locked group discount pricing (50% multiplier)"]
    M2 --> G3["• Dynamic capacity bounds (enrolled vs max)"]
    M2 --> G4["• Hourly low-attendance watchdog alert"]

    classDef mode fill:#1e1b4b,stroke:#a855f7,stroke-width:2px,color:#ffffff;
    classDef feature fill:#0f172a,stroke:#38bdf8,stroke-width:2px,color:#ffffff;

    class Root,M1,M2 mode;
    class F1,F2,F3,F4,G1,G2,G3,G4 feature;
```

---

## ⚡ 7. Concurrency Safety & Optimistic Locking Guard

During high-demand registration windows or popular group lobby launches, Eruscent prevents database race conditions using **JPA Optimistic Locking** (`ObjectOptimisticLockingFailureException`):

```mermaid
flowchart TD
    A["Student A (Enrolls in Lobby)"] --> C["Simultaneous Database Mutation Attempt"]
    B["Student B (Enrolls in Lobby)"] --> C
    
    C --> D["JPA Optimistic Locking Check (@Version)"]
    
    D --> E["1st Transaction Succeeds (Version Incremented)"]
    D --> F["2nd Transaction Fails (OptimisticLockingFailureException)"]
    
    F --> G["GlobalExceptionHandler Traps & Returns HTTP 409 Conflict"]

    classDef tx fill:#0f172a,stroke:#38bdf8,stroke-width:2px,color:#ffffff;
    classDef ok fill:#064e3b,stroke:#34d399,stroke-width:2px,color:#ffffff;
    classDef fail fill:#881337,stroke:#f43f5e,stroke-width:2px,color:#ffffff;

    class A,B,C,D tx;
    class E ok;
    class F,G fail;
```

---

## 🔎 8. Dynamic JPA Criteria API Search & Filtering Engine

The tutor marketplace directory uses a dynamic query specification builder (`TutorProfileSpecifications.java`) built on Spring Data JPA Criteria API:

```mermaid
flowchart TD
    A["Search Request (campusId, searchTerm, maxPrice, minRating)"] --> B["CriteriaBuilder Predicate Assembly"]
    
    B --> P1["• campusId Filter (Join User -> Campus UUID)"]
    B --> P2["• Mandatory Guard (User.isVerified = true)"]
    B --> P3["• Search Term Match (OR Name, Bio, Subject, Course Code)"]
    B --> P4["• Budget Filter (hourlyRate <= maxPrice)"]
    B --> P5["• Quality Threshold (rating >= minRating)"]
    
    P1 & P2 & P3 & P4 & P5 --> C["Execute Deduplicated Distinct Query (query.distinct(true))"]

    classDef spec fill:#1e1b4b,stroke:#a855f7,stroke-width:2px,color:#ffffff;
    classDef pred fill:#0f172a,stroke:#38bdf8,stroke-width:2px,color:#ffffff;

    class A,B,C spec;
    class P1,P2,P3,P4,P5 pred;
```

---

## 💬 9. Zero-Trust In-Session Peer Chat & Notification Radar

Eruscent provides encrypted, participant-restricted peer messaging (`MessageService.java`) for active sessions:

```mermaid
flowchart TD
    A["Chat Access Request (referenceId, referenceType, currentUser)"] --> B["Access Guard Bouncer (validateUserAccess)"]
    
    B -- "PRIVATE" --> C{"Principal is Student OR Tutor?"}
    C -- "YES" --> D["Grant Access & Fetch Chat History"]
    C -- "NO" --> E["❌ Access Denied"]

    B -- "GROUP" --> F{"Principal is Tutor OR Active Enrolled Student?"}
    F -- "YES & Active" --> D
    F -- "Canceled Enrollment" --> G["❌ Access Revoked"]

    classDef req fill:#1e1b4b,stroke:#818cf8,stroke-width:2px,color:#ffffff;
    classDef check fill:#0f172a,stroke:#38bdf8,stroke-width:2px,color:#ffffff;
    classDef deny fill:#881337,stroke:#f43f5e,stroke-width:2px,color:#ffffff;
    classDef pass fill:#064e3b,stroke:#34d399,stroke-width:2px,color:#ffffff;

    class A req;
    class B,C,F check;
    class D pass;
    class E,G deny;
```

---

## ⭐ 10. Verified Session Review & Math-Rounded Rating Engine

Tutor review submission and rating aggregation are governed by strict verification pipelines (`ReviewService.java`):

```mermaid
flowchart TD
    A["Review Submission Request (rating, comment, sessionId/groupSessionId)"] --> B["1. Verify Session Participation & Status = COMPLETED"]
    B --> C["2. Anti-Self-Review Guard (Ensure Student ID != Tutor ID)"]
    C --> D["3. Duplicate Review Check (existsBySessionId)"]
    D --> E["4. Save Review & Recalculate Aggregate Rating"]
    E --> F["Math.round(newAverage * 10.0) / 10.0 ──► Update TutorProfile"]

    classDef step fill:#1e1b4b,stroke:#818cf8,stroke-width:2px,color:#ffffff;
    classDef pass fill:#064e3b,stroke:#34d399,stroke-width:2px,color:#ffffff;

    class A,B,C,D,E step;
    class F pass;
```

---

## 🔥 11. Timezone-Aware Gamification & Activity Streak Engine

To encourage consistent peer learning, Eruscent tracks daily activity streaks for both students and tutors (`updateStreak` in `GroupSessionService` & `TutoringSessionService`).

```mermaid
flowchart TD
    A["Session Completed Event"] --> B["Extract User Timezone (e.g. 'Asia/Manila', 'America/New_York')"]
    B --> C["Convert UTC Timestamp to User ZonedDateTime"]
    C --> D{"Compare Local Date vs Last Streak Date"}
    
    D -- "Yesterday (todayLocal - 1)" --> E["🔥 Increment Streak Count++"]
    D -- "Today (Same Local Day)" --> F["Maintain Current Streak"]
    D -- "< Yesterday (Missed Day)" --> G["Reset Streak Count to 1"]

    classDef event fill:#1e1b4b,stroke:#818cf8,stroke-width:2px,color:#ffffff;
    classDef math fill:#0f172a,stroke:#38bdf8,stroke-width:2px,color:#ffffff;
    classDef act fill:#064e3b,stroke:#34d399,stroke-width:2px,color:#ffffff;

    class A event;
    class B,C,D,G math;
    class E,F act;
```

---

# PART III: SECURITY, RESILIENCE & EXCEPTION CONTRACTS

## 🔒 12. OWASP-Hardened Security & Multi-Subdomain CORS Matrix

Eruscent was subjected to a comprehensive security engineering audit, implementing multi-layered controls against OWASP Top 10 vulnerabilities and cross-origin attacks.

```mermaid
flowchart TD
    A["AUDIT EVENT GENERATED"] --> B["1. PII & Secret Scrubbing (Regex Redaction)"]
    B --> C["2. Log Forging & XSS Sanitization (CRLF & HtmlUtils)"]
    C --> D["3. HMAC-SHA256 Digital Signature Generation"]
    D --> E["4. Asynchronous DB Persistence (auditExecutor)"]

    classDef sec fill:#1e1b4b,stroke:#c084fc,stroke-width:2px,color:#ffffff;
    classDef act fill:#0f172a,stroke:#38bdf8,stroke-width:2px,color:#ffffff;

    class A,E sec;
    class B,C,D act;
```

---

## 🛡️ 13. Rate Limiting & Denial-of-Service (DoS) Protection Matrix

Gateway rate limiting is managed by `RateLimitInterceptor` using **Bucket4j**:

| Rate Limit Profile | URI Patterns / Protected Endpoints | Allowance Threshold | Bucket Refill Strategy | Action on Overflow |
|---|---|---|---|---|
| **Auth Profile** | `/api/v1/auth/**`, `/api/v1/users/login`, `/api/v1/users/register` | **5 requests / minute** | Per-IP Token Bucket | HTTP 429 Too Many Requests |
| **Public Contact Profile** | `/api/v1/public/contact` | **2 requests / hour** | Per-IP Token Bucket | HTTP 429 Too Many Requests |
| **State Mutation Profile** | All state-modifying requests (`POST`, `PUT`, `DELETE`, `PATCH`) | **60 requests / minute** | Per-IP Token Bucket | HTTP 429 Too Many Requests |
| **Read Bypass** | All `GET` and `OPTIONS` pre-flight requests | **Unlimited / Unthrottled** | Bypass Rule | Allowed |

---

## 🔄 14. Resilient Client Interceptor & Automatic Retry Engine

The Next.js frontend client (`apiClient.ts`) is fortified with an intelligent HTTP resilience pipeline built on Axios:

```mermaid
flowchart TD
    A["Client API Call (apiClient)"] --> B["1. Bearer Token Async Guard (Polls Clerk)"]
    B --> C["2. Execute HTTP Request"]
    
    C -- "200 OK" --> D["Return Payload"]
    C -- "Transient Error (502, 503, 504, 429, Timeout)" --> E["3. Exponential Backoff Retry (Max 2 Retries, 1s Delay)"]
    
    E -- "Retry Succeeds" --> D
    E -- "Retries Exhausted" --> F["Extract Structured Error Message for UI Toast"]

    classDef client fill:#0369a1,stroke:#38bdf8,stroke-width:2px,color:#ffffff;
    classDef retry fill:#9a3412,stroke:#fb923c,stroke-width:2px,color:#ffffff;
    classDef ok fill:#064e3b,stroke:#34d399,stroke-width:2px,color:#ffffff;

    class A,B,C client;
    class D ok;
    class E,F retry;
```

---

## 📐 15. Uniform Enterprise Exception Contract & ISO-8601 Serialization

Eruscent enforces a unified, RFC 7807 compliant error contract managed by `GlobalExceptionHandler` (`@RestControllerAdvice`) and customized Jackson temporal serialization (`JacksonConfig.java`):

```mermaid
sequenceDiagram
    autonumber
    participant UI as 📱 Next.js React UI Component
    participant Axios as ⚡ apiClient.ts (Frontend Interceptor)
    participant Ctrl as 🎮 GroupSessionController.java
    participant Service as ⚙️ GroupSessionService.java
    participant Handler as 🛡️ GlobalExceptionHandler.java
    participant DTO as 📄 ApiErrorResponse.java

    UI->>Axios: DELETE /api/v1/lobbies/enrollments/{id}
    Axios->>Ctrl: Forward HTTP Request with Bearer Token
    Ctrl->>Service: groupSessionService.dropOutStudent(enrollmentId, studentId)
    
    Note over Service: Business Rule Check Failure!<br/>(Time remaining < 24 Hours)
    Service-->>Ctrl: throw new IllegalStateException("Cancellations must be made at least 24 hours in advance.")
    Ctrl-->>Handler: Exception bubbles up to @RestControllerAdvice
    
    Handler->>DTO: new ApiErrorResponse(400, "Business Rule Violation", ex.getMessage())
    Note over DTO: Auto-injects LocalDateTime.now()<br/>Jackson Formats ISO-8601 JSON
    DTO-->>Handler: Returns ApiErrorResponse Record Instance
    Handler-->>Axios: HTTP 400 Bad Request JSON Payload
    
    Note over Axios: apiClient response interceptor extracts:<br/>error.response.data.message
    Axios-->>UI: Rejects Promise with extractedMessage
    UI->>UI: toast.error("Cancellations must be made at least 24 hours in advance.")
```

```json
{
  "status": 409,
  "error": "Business Rule Violation",
  "message": "Schedule conflict! You already have another session during this time.",
  "timestamp": "2026-08-09T02:16:03.123Z"
}
```

---

# PART IV: TELEMETRY, PERFORMANCE & BACKGROUND ENGINES

## ⚙️ 16. High-Concurrency Asynchronous & Scheduled Engine

Eruscent combines dedicated thread pools with automated background schedulers to guarantee high throughput and clean data maintenance.

```mermaid
flowchart TD
    Root["⚡ SPRING @ENABLEASYNC THREAD POOLS"]
    Root --> P1["auditExecutor Pool (2 Core / 5 Max / 100 Queue)"]
    Root --> P2["taskExecutor Pool (5 Core / 10 Max / 500 Queue)"]

    P1 --> I1["• Isolates HMAC Audit Logging"]
    P2 --> I2["• Handles Email Notifications & Webhooks"]

    classDef pool fill:#1e1b4b,stroke:#818cf8,stroke-width:2px,color:#ffffff;
    classDef item fill:#0f172a,stroke:#38bdf8,stroke-width:2px,color:#ffffff;

    class Root,P1,P2 pool;
    class I1,I2 item;
```

---

## 🚀 17. In-Memory Telemetry & Treemap Caching Engine (`@Cacheable`)

To maintain ultra-low response latency across large multi-tenant institutional networks, Eruscent incorporates **Spring Cache Abstraction** (`@Cacheable` in `SuperAdminTelemetryService`):

```mermaid
flowchart TD
    A["Super Admin Dashboard Request (getGlobalKpis / getGlobalHeatmap)"] --> B["Check Spring Cache Region ('globalKpis' / 'globalHeatmap')"]
    
    B -- "Cache Hit" --> C["⚡ Return Cached Telemetry DTO (Zero DB Latency)"]
    B -- "Cache Miss" --> D["Execute Multi-Tenant SQL Aggregation Query"]
    D --> E["Populate Cache Region & Return Telemetry Payload"]

    classDef req fill:#1e1b4b,stroke:#818cf8,stroke-width:2px,color:#ffffff;
    classDef cache fill:#0f172a,stroke:#38bdf8,stroke-width:2px,color:#ffffff;
    classDef hit fill:#064e3b,stroke:#34d399,stroke-width:2px,color:#ffffff;

    class A req;
    class B,D,E cache;
    class C hit;
```

---

## 📈 18. Institutional Analytics & Departmental Bottleneck Telemetry

Eruscent equips department heads and platform operators with real-time academic telemetry:

```mermaid
flowchart LR
    A["Department Session Logs"] --> B["Query Aggregator"] --> C["Department KPI Telemetry"]

    classDef src fill:#1e1b4b,stroke:#818cf8,stroke-width:2px,color:#ffffff;
    classDef res fill:#064e3b,stroke:#34d399,stroke-width:2px,color:#ffffff;

    class A,B src;
    class C res;
```

---

## 🪵 19. Production Structured Telemetry & Observability Pipeline

Eruscent emits security and operational telemetry via SLF4J (`SecurityConfig.java`), which formats clean log streams for production log aggregation:

```log
2026-08-08T23:15:50.123+08:00 DEBUG 14208 --- [backend] [http-nio-8080-exec-1] c.s.backend.config.SecurityConfig       : >>> SECURITY TELEMETRY: ClerkId=user_2tX9kL...7mP, UserFound=true, ResolvedRoles=[ROLE_STUDENT, ROLE_TUTOR], MappedAuthorities=[ROLE_STUDENT, ROLE_TUTOR]
```

---

# PART V: DEVOPS, SCHEMA & REFERENCE SCHEMAS

## 🛠️ 20. Automated CI/CD Pipeline & Full-Stack DevOps Architecture

Eruscent uses an automated, containerized **GitHub Actions** CI/CD testing and vulnerability auditing pipeline (`.github/workflows/`):

```mermaid
flowchart TD
    A["Pull Request / Push to Main Branch"] --> B["Java CI Workflow (ci.yml)"]
    A --> C["Security Audit Workflow (security-audit.yml)"]

    B --> B1["• Spins up PostgreSQL 16 Service Container (pg_isready)"]
    B --> B2["• Compiles Java 21 & Runs Unit Tests"]

    C --> C1["• Runs npm audit --audit-level=high (Frontend)"]
    C --> C2["• Runs mvn clean verify (Backend)"]
    C --> C3["• Scheduled Weekly Midnight Audits (Cron: 0 0 * * 0)"]

    classDef trigger fill:#1e1b4b,stroke:#818cf8,stroke-width:2px,color:#ffffff;
    classDef job fill:#0f172a,stroke:#38bdf8,stroke-width:2px,color:#ffffff;

    class A trigger;
    class B,C,B1,B2,C1,C2,C3 job;
```

---

## 🏗️ 21. Environment Profile Isolation & 12-Factor Production Tiering

Eruscent complies with cloud-native 12-Factor Application principles through dynamic Spring profile tiering (`application.properties` vs `application-prod.properties`):

```mermaid
flowchart TD
    Root["SPRING ENVIRONMENT TIER SELECTION"] --> D["Development Profile (Local)"]
    Root --> P["Production Profile (Railway / Cloud)"]

    D --> D1["• Local PostgreSQL (strive_db)"]
    D --> D2["• Mailtrap SMTP Sandbox"]

    P --> P1["• Managed Cloud Postgres with SSL"]
    P --> P2["• Enterprise SMTP Notification Gateway"]

    classDef root fill:#1e1b4b,stroke:#a855f7,stroke-width:2px,color:#ffffff;
    classDef dev fill:#0f172a,stroke:#38bdf8,stroke-width:2px,color:#ffffff;
    classDef prod fill:#064e3b,stroke:#34d399,stroke-width:2px,color:#ffffff;

    class Root root;
    class D,D1,D2 dev;
    class P,P1,P2 prod;
```

---

## 🐘 22. Versioned Schema Evolution & Automated Seeder Engine

Database structure, migrations, and development seeders are managed via **Flyway** and Spring Boot initialization beans:

```mermaid
flowchart LR
    V1["V1__init_schema.sql<br/>• Core Entities & Indexes"] --> V2["V2__add_group_sessions.sql<br/>• Group Lobbies & Capacity"] --> V3["V3__add_user_roles.sql<br/>• Role Enums & Audit Signatures"]

    classDef flyway fill:#881337,stroke:#f43f5e,stroke-width:2px,color:#ffffff;

    class V1,V2,V3 flyway;
```

---

## 📖 23. OpenAPI 3.0 & Interactive Swagger UI Pipeline

Eruscent automatically compiles its backend route contracts into an interactive **OpenAPI 3.0** documentation suite powered by `springdoc-openapi-starter-webmvc-ui`:

```mermaid
flowchart TD
    A["Spring Boot REST Controllers"] --> B["springdoc-openapi Annotation & Reflection Engine"]
    B --> C["Interactive Swagger UI (/swagger-ui.html)"]
    B --> D["OpenAPI 3.0 JSON Contract (raw-openapi.json)"]

    classDef doc fill:#1e1b4b,stroke:#85ea2d,stroke-width:2px,color:#ffffff;

    class A,B,C,D doc;
```

---

## 📊 24. Entity-Relationship & Data Model Overview

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
    GROUP_SESSION ||--o| REVIEW : receives_group_review
    USER ||--o{ SESSION_MESSAGE : sends
    USER ||--o{ PROFILE_VIEW : views_tutor_profile
    USER ||--o{ AUDIT_LOG : triggers
    UNIVERSITY ||--o{ ALLOWED_EMAIL_DOMAIN : enforces

    USER {
        bigint id PK
        string clerk_id UK
        string email UK
        string full_name
        string profile_picture_url
        integer streak_count
        timestamp last_streak_date
        string timezone
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
        integer enrolled_count
        decimal locked_ticket_price
        boolean low_attendance_warning_sent
        enum status
    }

    PROFILE_VIEW {
        uuid id PK
        uuid viewer_id FK
        uuid tutor_id FK
        timestamp view_date
    }

    SESSION_MESSAGE {
        bigint id PK
        bigint sender_id FK
        uuid reference_id
        string reference_type
        string content
        timestamp created_at
    }

    REVIEW {
        bigint id PK
        bigint student_id FK
        bigint tutor_id FK
        bigint session_id FK
        bigint group_session_id FK
        integer rating
        string comment
        timestamp created_at
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

## 🎯 25. Feature Capability & System Architecture Mapping

| Feature Capability | Functional Description | Architecture Component | Primary Security & Operational Control |
|---|---|---|---|
| **Domain-Gated Signup** | Restricts student registration to verified university email domains | `EmailDomainController` & `AllowedEmailDomain` | Super Admin managed, real-time DB allowlist check |
| **Tutor Marketplace** | Searchable directory by subject, campus, hourly rate, and rating | `TutorProfileController` & JPA Specifications | Public GET cache, active profile filtering |
| **Dynamic Search** | Multi-field search across names, bios, subjects, and course codes | `TutorProfileSpecifications` | Criteria API, distinct deduplication |
| **1:1 Session Engine** | Real-time booking calendar, time slot locks, session state machine | `TutoringSessionService` | IDOR owner isolation, pending auto-expiry |
| **Group Session Lobbies**| Multi-student group sessions, capacity bounds, automated enrollment | `GroupSessionService` & `Enrollment` | Capacity checks, hourly low-attendance watchdog |
| **Peer Chat Radar** | Participant-restricted chat with dynamic enrollment revocation | `MessageService` & `SessionMessage` | Access bouncer, batch notification radar |
| **Verified Reviews** | Student review submission for completed sessions with rating math | `ReviewService` & `Review` | Completion checks, anti-self-review guard |
| **Concurrency Guard** | Prevents double-booking during concurrent seat claims | JPA Optimistic Locking | `@Version` fields, HTTP 409 Conflict handling |
| **Tutor Analytics** | 7-day earnings yield, retention rate, daily yield analytics | `TutorAnalyticsController` | Custom SQL DTO projections, read-only isolation |
| **Gamification Engine** | Timezone-aware streak tracking for active students and tutors | `GroupSessionService` & `UserService` | User timezone validation, streak boundary math |
| **In-Memory Caching** | Spring `@Cacheable` optimization for telemetry and heatmaps | `SuperAdminTelemetryService` | Cache key eviction, zero DB reload latency |
| **Interactive API Docs**| Self-documenting Swagger UI & OpenAPI 3.0 specification | `springdoc-openapi` & `SwaggerConfig` | Bearer JWT security scheme definition |
| **Automated CI/CD** | Live PostgreSQL 16 container integration builds & weekly audits | GitHub Actions (`ci.yml` & `security-audit.yml`) | PR build checks, `npm audit` & Maven verification |
| **Department Admin Portal**| Tutor verification workflows, 30-day KPI snapshots, subject bottlenecks | `AdminController` | Department-scoped queries, `@PreAuthorize("hasRole('ADMIN')")` |
| **Super Admin HUD** | Platform-wide telemetry, system anomalies, domain allowlist manager | `SuperAdminController` & `SuperAdminTelemetryController` | Platform RBAC, zero-downtime allowlist updates |

---

## 🗺️ 26. High-Level API Domain Map

All API endpoints are exposed under the `/api/v1` namespace:

| Group | Base Path | Required Access / Role | Rate Limit Profile | Purpose |
|---|---|---|---|---|
| **Auth** | `/api/v1/auth/**` | Public / Authenticated | Auth Profile (5 req/min) | Identity synchronization & session context |
| **Users** | `/api/v1/users/**` | Authenticated / Self | Auth Profile (sensitive routes) | User profiles & identity self-healing |
| **Sessions (1:1)** | `/api/v1/sessions/**` | `ROLE_STUDENT`, `ROLE_TUTOR` | Standard Profile (60 req/min) | 1-on-1 session booking state machine |
| **Group Lobbies** | `/api/v1/lobbies/**` | `ROLE_STUDENT`, `ROLE_TUTOR` | Standard Profile (60 req/min) | Group session creation & auto-enrollment |
| **Messages (Chat)**| `/api/v1/messages/**` | `ROLE_STUDENT`, `ROLE_TUTOR` | Standard Profile (60 req/min) | Peer chat history & real-time notifications |
| **Reviews** | `/api/v1/reviews/**` | `ROLE_STUDENT` | Standard Profile (60 req/min) | Verified session review submission |
| **Availability** | `/api/v1/timeslots/**` | `ROLE_TUTOR` | Standard Profile (60 req/min) | Tutor calendar time slot publishing |
| **Tutor Profiles** | `/api/v1/profiles/**` | Public / Authenticated | Read Bypass (GET) | Public tutor directory search |
| **Dashboard** | `/api/v1/dashboards/**` | Student, Tutor, Admin | Standard Profile (60 req/min) | Role-based aggregate dashboards |
| **Analytics** | `/api/v1/tutor/analytics` | `ROLE_TUTOR` | Standard Profile (60 req/min) | Tutor earnings yield & retention analytics |
| **Admin** | `/api/v1/admin/**` | `ROLE_ADMIN` | Standard Profile (60 req/min) | Tutor approval & department KPIs |
| **Super Admin** | `/api/v1/super/**` | `ROLE_SUPER_ADMIN` | Standard Profile (60 req/min) | Platform administration & domain allowlist |
| **Universities** | `/api/v1/universities/**` | Public | Read Bypass (GET) | Institutional campus lookup |

---

## 📱 27. Responsive Frontend & Mobile Layout Architecture

The frontend client layer is built with a modern, high-performance web architecture:

* **Framework**: Next.js 16 (App Router) with React 19 and TypeScript 5.
* **Styling System**: Tailwind CSS v4 with dynamic dark mode (`next-themes`) and Radix UI primitives.
* **Visual FX & Icons**: Lucide React icons, Framer Motion animations, and Canvas Confetti feedback.
* **State Management**: TanStack React Query (`v5`) handling API caching, optimistic UI updates, and stale-while-revalidate policies.

---

## 🛠️ 28. Technology Stack Breakdown

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
| **Identity Provider** | Clerk | `@clerk/nextjs` | Authentication, token issuance & avatar CDN |
| **Webhook Verifier** | Svix | `1.90.0` | Cryptographic HMAC webhook verification |
| **Rate Limiter** | Bucket4j | `8.10.1` | Per-IP token bucket rate limiting |
| **API Documentation** | OpenAPI / Swagger UI | `2.8.5` | Interactive API documentation & OpenAPI schemas |
| **CI/CD Automation** | GitHub Actions | Workflows | Live PostgreSQL container integration & security audits |
| **Database** | PostgreSQL | `16` | Relational data persistence |
| **Migrations** | Flyway | Built-in | Database versioning & automated migrations |
| **Email Service** | JavaMailSender | Spring Starter | Asynchronous transactional notification mail |

---

<div align="center">

**Designed & Architected by Eruscent**  
*Building Secure, Scalable, and Modern Enterprise Systems.*

</div>
