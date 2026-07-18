# KHARCHA

# 21_ARCHITECTURE_DECISION_RECORDS.md

---

# Document Information

| Field | Value |
|--------|-------|
| Product | Kharcha |
| Tagline | Every Rupee Matters |
| Version | 1.0 |
| Status | Living Document |
| Owner | Engineering Team |

---

# Purpose

This document records significant architectural and technical decisions made during the development of Kharcha.

Each Architecture Decision Record (ADR) captures:

- Context
- Problem
- Options considered
- Decision
- Rationale
- Consequences

The objective is to preserve engineering knowledge, reduce repeated discussions, and provide historical context for future contributors.

---

# ADR Template

Every decision follows the same structure.

## ADR-XXX

### Status

Proposed | Accepted | Superseded | Deprecated

### Date

YYYY-MM-DD

### Context

Why was this decision needed?

### Options Considered

- Option A
- Option B
- Option C

### Decision

Final decision.

### Rationale

Why this option was selected.

### Consequences

Positive

Negative

Future considerations

---

# ADR-001

## Backend Framework

### Status

Accepted

### Context

Kharcha requires a backend framework that is lightweight, fast, well-documented, and suitable for REST APIs.

### Options Considered

- FastAPI
- Django REST Framework
- Node.js (Express)
- NestJS

### Decision

Use **FastAPI**.

### Rationale

- Excellent performance
- Automatic OpenAPI documentation
- Strong typing
- Easy integration with Python AI libraries
- Modern asynchronous support

### Consequences

Positive

- Fast development
- Easy AI integration
- High performance

Negative

- Smaller ecosystem than Django

---

# ADR-002

## Database

### Status

Accepted

### Context

Kharcha stores structured financial information with strong relationships.

### Options Considered

- PostgreSQL
- MongoDB
- MySQL

### Decision

Use **PostgreSQL**.

### Rationale

- ACID compliance
- Excellent relational support
- Powerful indexing
- JSONB support for AI metadata
- Mature ecosystem

### Consequences

Positive

- Reliable financial transactions
- Strong data integrity
- Scalable

Negative

- Slightly more complex than document databases

---

# ADR-003

## Mobile Framework

### Status

Accepted

### Context

The application must support Android and iOS from a single codebase.

### Options Considered

- Flutter
- React Native
- Native Android + iOS

### Decision

Use **Flutter**.

### Rationale

- High-performance UI
- Single codebase
- Excellent developer experience
- Rich widget ecosystem

### Consequences

Positive

- Faster development
- Consistent UI
- Reduced maintenance

Negative

- Larger application size compared to native apps

---

# ADR-004

## Authentication Provider

### Status

Accepted

### Context

Secure authentication is required without building identity management from scratch.

### Options Considered

- Firebase Authentication
- Auth0
- Custom JWT Authentication

### Decision

Use **Firebase Authentication**.

### Rationale

- Secure
- Reliable
- Supports Google Sign-In
- Easy Flutter integration

### Consequences

Positive

- Reduced implementation effort
- Industry-standard authentication

Negative

- Vendor dependency

---

# ADR-005

## API Architecture

### Status

Accepted

### Context

The mobile application requires predictable communication with backend services.

### Options Considered

- REST
- GraphQL
- gRPC

### Decision

Use **REST APIs**.

### Rationale

- Simpler implementation
- Broad tooling support
- Easy debugging
- Appropriate for MVP

### Consequences

Positive

- Faster development
- Easier onboarding

Negative

- Over-fetching possible in some scenarios

---

# ADR-006

## AI Integration Strategy

### Status

Accepted

### Context

AI is a core differentiator for Kharcha.

### Options Considered

- Rule-based system only
- Large Language Model only
- Hybrid approach

### Decision

Use a **hybrid approach**.

### Rationale

- Deterministic calculations remain rule-based.
- Explanations and coaching use LLMs.

### Consequences

Positive

- Reliable financial calculations
- Natural AI interactions

Negative

- Additional architectural complexity

---

# ADR-007

## Expense Storage

### Status

Accepted

### Context

Users may edit or delete expenses.

### Decision

Expenses are stored as immutable financial records where possible, with audit fields (`created_at`, `updated_at`, `deleted_at`) to preserve history.

### Rationale

Financial applications benefit from traceability.

---

# ADR-008

## Financial Health Score

### Status

Accepted

### Context

The Financial Health Score is displayed frequently on the dashboard.

### Decision

The score is calculated from expense and budget data using defined business rules and stored as historical snapshots for trend analysis.

### Rationale

Historical records allow users to track improvement over time while keeping calculations reproducible.

---

# ADR-009

## AI Data Access

### Status

Accepted

### Context

AI requires user financial data to generate recommendations.

### Decision

AI services receive only the minimum required data for each request.

### Rationale

Supports the principle of data minimization and improves user privacy.

---

# ADR-010

## Offline Support

### Status

Planned

### Context

Users may want to record expenses without an internet connection.

### Decision

Offline-first support will be implemented after the MVP.

### Rationale

Prioritize core product delivery while designing the architecture to accommodate local storage and synchronization in future releases.

---

# Decision Review Process

A new ADR should be created when:

- Introducing a new technology.
- Replacing an existing technology.
- Changing architectural direction.
- Making a significant security decision.
- Adopting a third-party service.
- Introducing a major product capability.

Minor implementation details do not require an ADR.

---

# ADR Lifecycle

Proposed

↓

Review

↓

Accepted

↓

Implemented

↓

Reviewed

↓

Deprecated (if replaced)

---

# Related Documents

- 15_BACKEND_ARCHITECTURE.md
- 16_API_SPECIFICATION.md
- 17_DATABASE_SCHEMA.md
- 18_SECURITY_AND_PRIVACY.md
- 20_DEVELOPMENT_ROADMAP.md

---

# CEO Vision

Technology choices shape a product for years.

Every significant decision should be intentional, documented, and understandable.

The goal of an Architecture Decision Record is not to prove a decision was perfect.

It is to ensure future contributors understand **why** the decision was made, what alternatives were considered, and what trade-offs were accepted.

A well-maintained ADR log reduces confusion, accelerates onboarding, and preserves the engineering knowledge that turns a project into a lasting product.
