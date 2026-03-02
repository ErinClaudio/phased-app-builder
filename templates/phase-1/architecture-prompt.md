# Architecture Prompt Template

A structured guide for defining app architecture before building.

---

## How to Use

1. Copy this template to your project as `docs/architecture.md`
2. Select your primary stack (defaults will populate)
3. Answer guiding questions in each section
4. Log decisions as you make them (Section 7)

---

## 1. Project Overview

| Field | Value |
|-------|-------|
| **Project Name** | |
| **One-line Description** | |
| **Target Users** | |
| **Core Problem Solved** | |

### Guiding Questions
- What's the simplest way to describe this app?
- Who uses it and why?
- What's the one thing it *must* do well?

---

## 2. Stack Selection

### Primary Stack

Choose one. Defaults will apply based on selection.

- [ ] **Rails** — Full-stack web app
- [ ] **iOS (Swift)** — Native Apple mobile
- [ ] **Bridgetown** — Static/JAMstack site
- [ ] **Android (Kotlin)** — Native Android mobile *(coming soon)*
- [ ] **Other** — Specify: ___

---

## 3. Stack Defaults

*Auto-populated based on stack selection. Override as needed.*

### Rails Defaults
| Component | Default | Override |
|-----------|---------|----------|
| Ruby version | 3.3+ | |
| Rails version | 7.1+ | |
| Database | PostgreSQL | |
| Background jobs | Solid Queue | |
| CSS | Tailwind | |
| JS | Hotwire (Turbo + Stimulus) | |
| Auth | Devise or custom | |
| Testing | RSpec | |
| Hosting | Fly.io | |
| CI/CD | GitHub Actions | |

### iOS (Swift) Defaults
| Component | Default | Override |
|-----------|---------|----------|
| iOS target | 17.0+ | |
| Swift version | 5.9+ | |
| UI framework | SwiftUI | |
| Data persistence | SwiftData / Core Data | |
| Networking | URLSession + async/await | |
| Auth | Sign in with Apple | |
| Testing | XCTest | |
| Distribution | App Store | |
| CI/CD | Xcode Cloud / GitHub Actions | |

### Bridgetown Defaults
| Component | Default | Override |
|-----------|---------|----------|
| Ruby version | 3.3+ | |
| Bridgetown version | 1.3+ | |
| CSS | Tailwind | |
| JS | esbuild | |
| CMS | None (markdown) | |
| Hosting | Netlify | |
| CI/CD | GitHub Actions | |

### Android (Kotlin) Defaults *(Template — Not Yet Configured)*
| Component | Default | Override |
|-----------|---------|----------|
| Min SDK | TBD | |
| Kotlin version | TBD | |
| UI framework | Jetpack Compose | |
| Data persistence | Room | |
| Networking | Retrofit / Ktor | |
| Auth | TBD | |
| Testing | JUnit / Espresso | |
| Distribution | Play Store | |
| CI/CD | GitHub Actions | |

---

## 4. Architecture Pattern

### Guiding Questions
- How complex is the domain logic?
- Will multiple clients (web, mobile, API) share a backend?
- Solo dev or team?

### Pattern Selection

| Pattern | Best For | Select |
|---------|----------|--------|
| **Monolith** | Solo/small team, fast iteration | [ ] |
| **API + SPA** | Separate frontend/backend teams | [ ] |
| **API + Mobile** | Mobile-first with shared backend | [ ] |
| **Static + API** | Content sites with dynamic features | [ ] |
| **Microservices** | Large teams, independent scaling | [ ] |

**Selected Pattern:** ___

**Rationale:** ___

---

## 5. Core Entities (Data Model Preview)

*High-level only — detailed model in Phase 1 Data Model Template*

| Entity | Key Attributes | Relationships |
|--------|----------------|---------------|
| | | |
| | | |
| | | |

### Guiding Questions
- What are the 3-5 main "things" in the system?
- What belongs to what?
- What can a user create/read/update/delete?

---

## 6. Constraints

| Constraint Type | Details |
|-----------------|---------|
| **Budget** | |
| **Timeline** | |
| **Team size** | |
| **Must integrate with** | |
| **Compliance/Legal** | |
| **Platform restrictions** | |

### Guiding Questions
- What's non-negotiable?
- What would change everything if it changed?
- Any third-party dependencies locked in?

---

## 7. Decision Log

*Record architectural decisions here. When you revisit this project in 3+ months, you'll know why you made each choice.*

### How to Log Decisions
- Add a row when you make a non-obvious choice
- "Why" = what problem this solved, or what you avoided
- Update if a decision changes

### Decisions

| Date | Decision | Choice | Options Considered | Why |
|------|----------|--------|-------------------|-----|
| | Stack | | | |
| | Architecture | | | |
| | Database | | | |
| | Auth | | | |
| | Hosting | | | |
| | | | | |

### Example Entries

| Date | Decision | Choice | Options Considered | Why |
|------|----------|--------|-------------------|-----|
| 2024-01-15 | Background jobs | Solid Queue | Sidekiq, Solid Queue, GoodJob | Rails 8 default, no Redis needed, simpler ops for solo dev |
| 2024-01-15 | Auth | Custom | Devise, Rodauth, Custom | Simple app with only email/password, Devise overkill |
| 2024-01-20 | File uploads | Active Storage + S3 | Active Storage + Disk, Shrine | Need CDN + permanent storage, AS is built-in |

---

## 8. Exit Checklist (Phase 1 → Phase 2)

- [ ] Project overview complete
- [ ] Stack selected with defaults reviewed
- [ ] Architecture pattern chosen with rationale
- [ ] Core entities identified
- [ ] Constraints documented
- [ ] Key decisions logged

**Ready for Phase 2 (Design)?** [ ] Yes / [ ] No — Blockers: ___

---

## Changelog

| Date | Change |
|------|--------|
| | Initial creation |
