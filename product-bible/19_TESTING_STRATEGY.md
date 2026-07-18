# KHARCHA

# 19_TESTING_STRATEGY.md

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

This document defines the testing strategy for Kharcha.

Its objective is to ensure that every release is reliable, secure, performant, and provides a consistent user experience.

Testing is not a final step before release—it is integrated throughout the development lifecycle.

---

# Quality Objectives

Every release should be:

- Correct
- Stable
- Secure
- Fast
- User-friendly
- Accessible
- Regression-free

---

# Testing Principles

Kharcha follows these testing principles:

- Test early
- Automate wherever practical
- Validate business rules
- Test real user journeys
- Prevent regressions
- Measure quality continuously

---

# Testing Levels

| Level | Purpose | Owner |
|--------|---------|-------|
| Unit Testing | Validate individual functions | Developer |
| Integration Testing | Verify module interactions | Developer |
| API Testing | Validate REST APIs | Backend Team |
| UI Testing | Validate screens and navigation | Flutter Team |
| End-to-End Testing | Verify complete user journeys | QA |
| Performance Testing | Measure responsiveness | QA |
| Security Testing | Validate security controls | QA / Security |
| User Acceptance Testing | Confirm business expectations | Product Owner |

---

# Unit Testing

Purpose

Ensure individual business logic functions behave correctly.

Examples

- Budget calculation
- Financial Health score calculation
- Expense validation
- AI recommendation rules
- Date utilities

Target Coverage

Minimum 80%

---

# Integration Testing

Purpose

Ensure services communicate correctly.

Examples

- Expense → Budget update
- Expense → Financial Health recalculation
- Expense → AI Insight generation
- Login → Dashboard loading

---

# API Testing

Every API endpoint must be tested.

Validation includes:

- Request validation
- Response format
- Authentication
- Authorization
- Error handling
- Status codes
- Rate limiting

Example

POST /expenses

Verify

✓ Valid request returns 201

✓ Missing amount returns 400

✓ Invalid token returns 401

✓ Unauthorized expense update returns 403

---

# Database Testing

Verify:

- CRUD operations
- Foreign key constraints
- Index performance
- Soft delete
- Transactions
- Data consistency

---

# Flutter UI Testing

Each screen should be tested for:

- Layout rendering
- Navigation
- Form validation
- Error messages
- Loading states
- Empty states
- Offline handling

Priority Screens

- Login
- Home Dashboard
- Add Expense
- Insights
- Budget
- AI Coach

---

# End-to-End Testing

Critical user journeys must be verified before every release.

## Journey 1

New User

Signup

↓

Budget Setup

↓

Add First Expense

↓

Dashboard Updates

↓

Financial Health Appears

↓

AI Insight Generated

---

## Journey 2

Existing User

Login

↓

Dashboard

↓

Add Expense

↓

Budget Updates

↓

Insights Refresh

↓

Logout

---

## Journey 3

AI Coach

Open AI Coach

↓

Ask Question

↓

Receive Recommendation

↓

Conversation Saved

---

# Performance Testing

Target response times:

| Operation | Target |
|-----------|--------|
| App Launch | < 3 sec |
| Login | < 2 sec |
| Dashboard | < 300 ms |
| Expense Save | < 200 ms |
| Search | < 500 ms |
| AI Response | < 3 sec |

Stress testing should verify the system remains stable under expected peak usage.

---

# Security Testing

Verify:

- Authentication
- Authorization
- Password protection
- JWT validation
- SQL Injection prevention
- XSS prevention
- Rate limiting
- Secure API access

No release should proceed with unresolved critical security vulnerabilities.

---

# Compatibility Testing

Supported Platforms

| Platform | Minimum Version |
|----------|-----------------|
| Android | Android 8.0 (API 26) |
| iOS | iOS 15 |

Verify:

- Different screen sizes
- Dark Mode
- Light Mode
- Slow network
- Limited storage

---

# Accessibility Testing

Ensure the application supports:

- Readable typography
- Adequate color contrast
- Screen readers
- Touch targets
- Keyboard navigation (where applicable)

Accessibility should be considered throughout development, not added later.

---

# Regression Testing

Regression testing is required whenever:

- A new feature is added
- A bug is fixed
- A dependency is upgraded
- The backend API changes
- AI logic is modified

Core workflows must continue to function after every change.

---

# Test Data

Testing should use:

- Dummy user accounts
- Sample expense data
- Mock AI responses
- Non-production databases

Production user data must never be used for development or testing.

---

# Bug Lifecycle

Bug Report

↓

Triage

↓

Assigned

↓

Fix Implemented

↓

Code Review

↓

Retest

↓

Closed

---

# Release Checklist

Before every production release:

☐ Unit tests passed

☐ Integration tests passed

☐ API tests passed

☐ UI tests passed

☐ End-to-end tests passed

☐ Security tests completed

☐ Performance targets met

☐ Regression tests completed

☐ Crash-free build verified

☐ Release notes prepared

---

# Quality Metrics

| Metric | Target |
|--------|--------|
| Unit Test Coverage | ≥ 80% |
| API Success Rate | ≥ 99% |
| Crash-Free Sessions | ≥ 99.5% |
| Critical Bugs | 0 |
| High Severity Bugs | 0 |
| App Launch Success | ≥ 99% |

---

# Recommended Tools

| Area | Tool |
|------|------|
| Unit Testing | Flutter Test, pytest |
| API Testing | Postman |
| UI Testing | Flutter Integration Test |
| Performance | Firebase Performance |
| Crash Reporting | Firebase Crashlytics |
| Security | OWASP ZAP |
| CI/CD | GitHub Actions |

---

# Continuous Integration

Every code change should automatically trigger:

1. Build
2. Static code analysis
3. Unit tests
4. API tests
5. Integration tests
6. Security scan
7. Build artifact generation

A build should not be merged if mandatory quality checks fail.

---

# Related Documents

- 15_BACKEND_ARCHITECTURE.md
- 16_API_SPECIFICATION.md
- 17_DATABASE_SCHEMA.md
- 18_SECURITY_AND_PRIVACY.md
- 20_DEVELOPMENT_ROADMAP.md

---

# CEO Vision

Quality is not measured by the number of features delivered.

Quality is measured by the confidence users have when they open the app, record an expense, and trust that every number is accurate.

Every successful test protects that trust.

Testing is not a cost.

It is an investment in reliability, reputation, and long-term product success.
