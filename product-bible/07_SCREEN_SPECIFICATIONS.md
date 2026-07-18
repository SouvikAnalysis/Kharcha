# KHARCHA

# 07_SCREEN_SPECIFICATIONS

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

This document defines every screen in Kharcha, its purpose, business value, user value, and relationship with other screens.

Every screen must exist to solve a real user problem.

If a screen does not create measurable value, it should not be built.

---

# Screen Strategy

Every screen should satisfy at least one of these objectives:

• Help users record financial data

• Help users understand their money

• Help users improve financial habits

• Help users configure the application

• Help users receive AI-powered guidance

---

# Screen Classification

| Type | Description |
|--------|------------|
| Core | Daily-use screens |
| Support | Occasionally used |
| Configuration | Setup & Settings |
| AI | Intelligence & Recommendations |
| Authentication | User Identity |

---

# Screen Inventory

| ID | Screen | Type | MVP | Daily Usage |
|----|---------|------|-----|------------|
| SC-01 | Splash | Authentication | ✅ | No |
| SC-02 | Welcome | Authentication | ✅ | No |
| SC-03 | Login / Signup | Authentication | ✅ | Rare |
| SC-04 | Budget Setup | Configuration | ✅ | No |
| SC-05 | Category Setup | Configuration | ✅ | Rare |
| SC-06 | Home Dashboard | Core | ✅ | Yes |
| SC-07 | Add Expense | Core | ✅ | Multiple Times |
| SC-08 | Expense Details | Support | ✅ | Occasionally |
| SC-09 | Insights | Core | ✅ | Weekly |
| SC-10 | Budget | Core | ✅ | Weekly |
| SC-11 | Search | Support | ✅ | Occasionally |
| SC-12 | Profile | Configuration | ✅ | Rare |
| SC-13 | Settings | Configuration | ✅ | Rare |
| SC-14 | Forgot Password | Authentication | ✅ | Rare |
| SC-15 | Money Story | AI | V2 |
| SC-16 | Financial Health | AI | V2 |
| SC-17 | AI Financial Coach | AI | V3 |
| SC-18 | Smart Budget Planner | AI | V3 |

---

# Screen Specification Template

Every screen should follow the same structure.

---

## Screen ID

SC-06

---

## Screen Name

Home Dashboard

---

## Category

Core

---

## Purpose

Provide users with an immediate understanding of their financial situation.

---

## User Problem

"I don't know how much I've spent."

---

## Business Value

Increase daily engagement and encourage consistent expense tracking.

---

## Primary KPI

Daily Active Users

---

## Frequency

Multiple times per day.

---

## Primary Components

• Greeting

• Financial Health Card

• Today's Spending

• Monthly Spending

• Remaining Budget

• Budget Progress

• Recent Expenses

• AI Daily Insight

• Floating Add Button

---

## Primary Actions

• Add Expense

• Open Insights

• Review Budget

• Search Expenses

• Open Profile

---

## Data Required

• User

• Salary

• Budget

• Expenses

• AI Summary

---

## Success Criteria

Users should understand their financial status within five seconds.

---

## Future AI Opportunities

• Daily Financial Brief

• Smart Alerts

• Personalized Tips

• Spending Prediction

• Savings Recommendation

---

## Related Screens

Add Expense

Insights

Budget

Profile

---

# Navigation Matrix

| Current Screen | Next Screen |
|---------------|-------------|
| Splash | Welcome |
| Welcome | Login |
| Login | Home |
| Home | Add Expense |
| Home | Insights |
| Home | Budget |
| Home | Search |
| Home | Profile |
| Profile | Settings |

---

# Screen Lifecycle

Daily Journey

Splash

↓

Home

↓

Add Expense

↓

Dashboard Updated

↓

Close App

Weekly Journey

Home

↓

Insights

↓

Budget

↓

Money Story

Monthly Journey

Home

↓

Financial Health

↓

AI Coach

↓

Budget Planning

---

# AI Screen Roadmap

Phase 1

Traditional Expense Tracker

Phase 2

Insights

Money Story

Financial Health

Phase 3

AI Coach

Smart Budget

Savings Planner

Predictive Spending

Phase 4

Fully Personalized Financial Companion

---

# Screen Design Principles

Every screen should be:

• Simple

• Fast

• Focused

• Useful

• Mobile First

• Accessible

• Consistent

• AI Assisted

---

# Golden Rule

A user should never ask:

"Where do I go next?"

Navigation should always feel obvious.

---

# CEO Vision

We are not designing screens.

We are designing moments that help people make better financial decisions.

Every screen should answer one question:

**"How does this screen improve the user's financial life?"**
