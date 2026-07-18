# KHARCHA

# 16_API_SPECIFICATION.md

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

This document defines the REST APIs used by Kharcha.

It serves as the communication contract between:

- Flutter Mobile Application
- Backend Services
- AI System

This document focuses on API behavior, request/response structures, validation rules, and error handling.

Implementation details are documented separately in:

- 15_BACKEND_ARCHITECTURE.md
- 17_DATABASE_SCHEMA.md

---

# API Design Principles

Every API should be:

- RESTful
- Predictable
- Secure
- Fast
- Versioned
- Consistent
- Well documented

---

# Base URL

Development

```
http://localhost:8000/api/v1
```

Production

```
https://api.kharcha.com/api/v1
```

---

# API Standards

| Property | Value |
|----------|-------|
| Protocol | HTTPS |
| Architecture | REST |
| Data Format | JSON |
| Encoding | UTF-8 |
| Authentication | JWT Bearer Token |
| Versioning | URL Versioning (/api/v1) |

---

# Authentication

Every protected request must include:

```
Authorization: Bearer <JWT_TOKEN>
```

Public APIs

- Signup
- Login
- Forgot Password

Protected APIs

- Dashboard
- Expenses
- Budget
- Insights
- AI
- Profile
- Notifications

---

# Standard Response Format

## Success

```json
{
  "success": true,
  "message": "Expense added successfully.",
  "data": {}
}
```

---

## Failure

```json
{
  "success": false,
  "message": "Validation failed.",
  "errorCode": "EXPENSE_001"
}
```

---

# Authentication APIs

## Signup

| Property | Value |
|----------|-------|
| Method | POST |
| Endpoint | /auth/signup |
| Authentication | No |

Purpose

Create a new user account.

Request

```json
{
  "name": "Souvik Ghosh",
  "email": "souvik@example.com",
  "password": "********"
}
```

Response

```json
{
  "success": true,
  "message": "Account created successfully.",
  "data": {
    "token": "JWT_TOKEN"
  }
}
```

---

## Login

| Property | Value |
|----------|-------|
| Method | POST |
| Endpoint | /auth/login |
| Authentication | No |

Purpose

Authenticate an existing user.

---

## Logout

| Property | Value |
|----------|-------|
| Method | POST |
| Endpoint | /auth/logout |

---

## Refresh Token

| Property | Value |
|----------|-------|
| Method | POST |
| Endpoint | /auth/refresh |

---

# Dashboard APIs

## Get Dashboard

| Property | Value |
|----------|-------|
| Method | GET |
| Endpoint | /dashboard |
| Authentication | Yes |

Returns

- Greeting
- Financial Health
- Today's Snapshot
- Budget Intelligence
- Recent Expenses
- AI Daily Insight

---

# Expense APIs

## Get Expenses

| Property | Value |
|----------|-------|
| Method | GET |
| Endpoint | /expenses |

Query Parameters

| Parameter | Description |
|------------|-------------|
| page | Current page |
| limit | Records per page |
| category | Filter category |
| startDate | Filter from date |
| endDate | Filter to date |
| search | Search keyword |

---

## Get Expense

| Property | Value |
|----------|-------|
| Method | GET |
| Endpoint | /expenses/{id} |

Purpose

Retrieve one expense.

---

## Add Expense

| Property | Value |
|----------|-------|
| Method | POST |
| Endpoint | /expenses |

Purpose

Create a new expense.

Request

```json
{
  "amount": 320,
  "categoryId": 3,
  "merchant": "Swiggy",
  "date": "2026-07-20",
  "notes": "Lunch"
}
```

Business Process

1. Validate request
2. Save expense
3. Update budget
4. Recalculate Financial Health
5. Refresh AI insights
6. Return updated dashboard summary

---

## Update Expense

| Property | Value |
|----------|-------|
| Method | PUT |
| Endpoint | /expenses/{id} |

---

## Delete Expense

| Property | Value |
|----------|-------|
| Method | DELETE |
| Endpoint | /expenses/{id} |

---

# Category APIs

| Method | Endpoint | Purpose |
|---------|----------|---------|
| GET | /categories | List categories |
| POST | /categories | Create category |
| PUT | /categories/{id} | Update category |
| DELETE | /categories/{id} | Delete category |

---

# Budget APIs

## Get Budget

GET

/budget

---

## Create Budget

POST

/budget

---

## Update Budget

PUT

/budget

---

## Budget Intelligence

GET

/budget/intelligence

Returns

- Remaining Budget
- Time Progress
- Safe Daily Spend
- Overspending Risk
- AI Recommendation

---

# Insights APIs

GET

/insights

Returns

- Monthly Spending
- Weekly Trend
- Category Breakdown
- AI Summary

---

# Financial Health APIs

GET

/financial-health

Returns

- Current Score
- Score History
- Improvement Areas
- Recommendations

---

# Money Story APIs

GET

/money-story

Returns

- Monthly Story
- Achievements
- Challenges
- Savings
- Recommendations

---

# AI Coach APIs

## Ask AI

POST

/ai/chat

Request

```json
{
    "question":"Can I afford a ₹5000 purchase?"
}
```

Response

```json
{
    "answer":"..."
}
```

---

# Notification APIs

| Method | Endpoint |
|---------|----------|
| GET | /notifications |
| PUT | /notifications/read |
| DELETE | /notifications/{id} |

---

# Search APIs

GET

/search

Filters

- Keyword
- Category
- Date
- Amount

---

# Analytics APIs

POST

/analytics/events

Purpose

Upload anonymous analytics events.

---

# Receipt APIs (Future)

POST

/upload/receipt

Future Features

- OCR
- Auto Categorization
- AI Expense Extraction

---

# Validation Rules

| Field | Rule |
|--------|------|
| Amount | Required, greater than zero |
| Merchant | Maximum 100 characters |
| Notes | Maximum 250 characters |
| Budget | Greater than zero |
| Salary | Cannot be negative |

---

# HTTP Status Codes

| Code | Meaning |
|------|---------|
| 200 | Success |
| 201 | Created |
| 204 | No Content |
| 400 | Bad Request |
| 401 | Unauthorized |
| 403 | Forbidden |
| 404 | Not Found |
| 409 | Conflict |
| 422 | Validation Error |
| 429 | Too Many Requests |
| 500 | Internal Server Error |

---

# Error Codes

| Code | Description |
|------|-------------|
| AUTH_001 | Invalid credentials |
| AUTH_002 | Token expired |
| USER_404 | User not found |
| EXPENSE_001 | Invalid expense data |
| EXPENSE_404 | Expense not found |
| BUDGET_001 | Budget not configured |
| AI_001 | AI service unavailable |
| SERVER_500 | Unexpected server error |

---

# Pagination Standard

```json
{
  "page": 1,
  "limit": 20,
  "totalRecords": 340,
  "totalPages": 17
}
```

---

# Rate Limiting

| API | Limit |
|-----|-------|
| Login | 5 requests/minute |
| Expense APIs | 100 requests/minute |
| Search | 100 requests/minute |
| AI Coach | 30 requests/hour |

---

# Security

Every API request follows:

- HTTPS Only
- JWT Authentication
- Input Validation
- Output Sanitization
- Rate Limiting
- Secure Headers
- SQL Injection Protection
- XSS Protection

---

# API Versioning

Current Version

```
/api/v1
```

Future

```
/api/v2
```

Older versions remain supported during the deprecation period.

---

# Related Documents

- 15_BACKEND_ARCHITECTURE.md
- 17_DATABASE_SCHEMA.md
- 18_SECURITY_AND_PRIVACY.md

---

# CEO Vision

An API is not just an endpoint.

It is a promise between the backend and the client.

Every API should be:

- Predictable
- Fast
- Secure
- Consistent
- Easy to integrate

Frontend developers should never need to guess how an API behaves. This document should provide everything required to build and maintain the Kharcha mobile application with confidence.
