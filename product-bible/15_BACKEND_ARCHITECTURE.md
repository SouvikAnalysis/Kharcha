# KHARCHA

# 15_BACKEND_ARCHITECTURE.md

---

# Document Information

| Field | Value |
|--------|-------|
| Product | Kharcha |
| Tagline | Every Rupee Matters |
| Version | 1.0 |
| Status | Approved |
| Owner | Souvik Ghosh |

---

# Purpose

This document defines the backend architecture of Kharcha.

It describes how the backend is organized, how services interact, how data flows through the system, and the architectural decisions that support a scalable, secure, and maintainable application.

This document focuses on architecture rather than implementation details.

API specifications are documented separately in **16_API_SPECIFICATION.md**.

---

# Architecture Goals

The backend should be:

- Scalable
- Secure
- Reliable
- Fast
- Modular
- Easy to maintain
- AI-ready

Every architectural decision should support long-term product growth.

---

# System Overview

Kharcha follows a client-server architecture.

The Flutter application communicates with the backend through secure REST APIs.

The backend processes business logic, stores financial data, generates AI insights, and sends notifications back to users.

---

# High-Level Architecture

```text
Flutter Mobile App
        │
 HTTPS REST API
        │
 API Layer
        │
 Business Services
        │
 Database + AI + Notifications
```

---

# Technology Stack

| Layer | Technology | Purpose |
|--------|------------|---------|
| Mobile | Flutter | Cross-platform application |
| Backend | FastAPI | REST API development |
| Database | PostgreSQL | Store application data |
| Cache | Redis | Improve performance |
| Authentication | Firebase Authentication | Secure user login |
| Notifications | Firebase Cloud Messaging | Push notifications |
| AI | LLM + Prompt Engine | Personalized financial insights |
| Storage | Cloud Storage | Future receipt uploads |
| Analytics | Firebase Analytics | User behavior tracking |

---

# Core Backend Services

The backend is divided into independent services.

| Service | Responsibility |
|----------|---------------|
| Authentication Service | Login, Signup, Token Validation |
| User Service | Profile and Preferences |
| Expense Service | Expense Management |
| Category Service | Category Management |
| Budget Service | Budget Tracking |
| Insight Service | Reports and Analytics |
| Financial Health Service | Health Score Calculation |
| AI Service | Money Story and Recommendations |
| Notification Service | Push Notifications |
| Analytics Service | Event Tracking |

---

# Service Responsibilities

## Authentication Service

Purpose

Manage user identity and authentication.

Responsibilities

- User registration
- Login
- Password reset
- Token validation
- Session management

---

## User Service

Purpose

Manage user information.

Responsibilities

- Personal profile
- Salary
- Financial goals
- Preferences
- Notification settings

---

## Expense Service

Purpose

Manage all expense-related operations.

Responsibilities

- Add expense
- Update expense
- Delete expense
- Search expenses
- Expense history

Whenever an expense changes, this service notifies the Budget Service and AI Service.

---

## Category Service

Purpose

Manage expense categories.

Responsibilities

- Default categories
- Custom categories
- Category validation

---

## Budget Service

Purpose

Monitor monthly budgets.

Responsibilities

- Budget creation
- Budget updates
- Remaining budget calculation
- Safe daily spending
- Budget intelligence

---

## Insight Service

Purpose

Transform financial data into meaningful information.

Responsibilities

- Spending trends
- Monthly reports
- Category analysis
- Weekly summaries

---

## Financial Health Service

Purpose

Calculate the user's Financial Health Score.

Factors

- Budget discipline
- Savings habit
- Spending consistency
- Goal achievement

---

## AI Service

Purpose

Provide intelligent financial guidance.

Responsibilities

- Daily Insights
- Money Story
- Spending analysis
- Smart recommendations
- Financial Coach

---

## Notification Service

Purpose

Keep users informed.

Examples

- Budget alerts
- Reminder notifications
- Money Story ready
- Achievement notifications

---

## Analytics Service

Purpose

Collect anonymous product usage data.

Used for

- Product improvement
- Feature adoption
- AI evaluation
- Crash analysis

---

# Database Architecture

The backend stores structured financial data inside PostgreSQL.

Primary entities include:

- Users
- Expenses
- Categories
- Budgets
- Financial Goals
- Notifications
- Financial Health
- Money Stories

Detailed schema is documented in:

17_DATABASE_SCHEMA.md

---

# Data Flow

Whenever a user records an expense:

Step 1

Flutter sends the request.

↓

Step 2

Expense Service validates the request.

↓

Step 3

Expense is saved.

↓

Step 4

Budget Service recalculates remaining budget.

↓

Step 5

Financial Health Score updates.

↓

Step 6

AI generates new insights if necessary.

↓

Step 7

Dashboard returns updated information.

---

# AI Integration

The AI system does not directly modify user data.

Instead, it reads financial information and generates recommendations.

AI Inputs

- Expenses
- Budget
- Salary
- Financial Goals
- Spending History

AI Outputs

- Daily Insight
- Budget Intelligence
- Money Story
- Financial Coach Responses

---

# Notification Architecture

Notifications are triggered by backend events.

Examples

| Event | Notification |
|--------|--------------|
| Budget reaches 80% | Budget Warning |
| Monthly Story Ready | Money Story Available |
| No expenses for 3 days | Friendly Reminder |
| Financial Health improves | Achievement |

Notifications are delivered using Firebase Cloud Messaging.

---

# Security Architecture

Security is a core design principle.

Measures include:

- HTTPS communication
- JWT authentication
- Role-based authorization
- Input validation
- SQL injection protection
- XSS protection
- Rate limiting
- Secure password storage
- Encrypted database connections

Sensitive financial data is never exposed through analytics.

---

# Performance Strategy

Target response times:

| Operation | Target |
|-----------|--------|
| Dashboard | <300 ms |
| Expense Save | <200 ms |
| Budget Calculation | <150 ms |
| Search | <500 ms |
| AI Insight | <3 seconds |

Caching is used for frequently accessed data such as:

- Dashboard
- Categories
- Financial Health
- Budget Summary

---

# Deployment Overview

Production environment includes:

- Flutter Mobile Application
- Backend API
- PostgreSQL Database
- Redis Cache
- Firebase Services
- AI Provider
- Monitoring Platform

Development, Staging, and Production remain completely isolated.

---

# Monitoring

The backend continuously monitors:

- API health
- Server performance
- Database performance
- AI response time
- Crash reports
- Error rates
- Notification delivery

Monitoring ensures issues are detected before they affect users.

---

# Backup Strategy

Daily backups

Weekly full backups

Point-in-time recovery

Encrypted backup storage

Regular recovery testing

---

# Development Environment

Separate environments are maintained for:

- Local Development
- Testing
- Staging
- Production

Each environment uses independent configuration files and databases.

---

# Backend Folder Structure

backend/

├── src/

│   ├── auth/

│   ├── users/

│   ├── expenses/

│   ├── budgets/

│   ├── categories/

│   ├── insights/

│   ├── financial_health/

│   ├── ai/

│   ├── notifications/

│   ├── analytics/

│   └── shared/

├── migrations/

├── tests/

├── docs/

├── scripts/

├── docker/

├── requirements.txt

└── main.py

---

# Future Scalability

The architecture supports future modules including:

- Receipt OCR
- Voice Expense Entry
- Family Accounts
- Multi-Currency
- Investment Tracking
- Subscription Detection
- Offline Synchronization
- Web Dashboard

These features can be added without major architectural changes.

---

# Related Documents

- 08_DATA_ARCHITECTURE.md
- 13_AI_SYSTEM.md
- 14_ANALYTICS_EVENTS.md
- 16_API_SPECIFICATION.md
- 17_DATABASE_SCHEMA.md
- 18_SECURITY_AND_PRIVACY.md

---

# CEO Vision

The backend should be invisible to users.

Users should experience:

- Fast performance
- Reliable synchronization
- Accurate financial insights
- Secure data handling
- Consistent application behavior

A successful backend is one that users never notice—but always trust.
