# KHARCHA

# 12_DESIGN_TOKENS.md

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

This document defines the design tokens used throughout Kharcha.

Design Tokens are reusable visual values that ensure consistency across:

- Flutter
- Figma
- Documentation
- Future Web Version

Every screen and component should use these tokens.

---

# Design Principles

The UI should feel:

- Calm
- Modern
- Trustworthy
- Minimal
- Premium

Money creates stress.

Kharcha should reduce stress.

---

# Color System

## Primary Color

Kharcha Teal

HEX

#44B8A8

Usage

- Primary Buttons
- FAB
- Active Navigation
- Progress Indicators
- Positive Charts

---

## Secondary Color

HEX

#2D6A73

Usage

- Secondary Actions
- Supporting Icons
- Card Highlights

---

## Accent Color

HEX

#FFC857

Usage

- Coin Animation
- Achievements
- Rewards
- Highlights

---

## Success

HEX

#34C759

Usage

- Success Messages
- Budget On Track
- Positive AI Insights

---

## Warning

HEX

#FF9F0A

Usage

- Overspending
- Budget Alerts

---

## Error

HEX

#FF3B30

Usage

- Validation
- Failed Requests

---

## Background

Primary

#F8FAFC

Secondary

#FFFFFF

Card Background

#FFFFFF

---

# Text Colors

Primary

#1E293B

Secondary

#64748B

Disabled

#CBD5E1

Inverse

#FFFFFF

---

# Typography

## Font Family

Primary

Inter

Fallback

Roboto

---

## Display

32px

Bold

Used For

Splash

---

## Heading 1

28px

Bold

---

## Heading 2

24px

SemiBold

---

## Heading 3

20px

SemiBold

---

## Title

18px

Medium

---

## Body

16px

Regular

---

## Caption

14px

Regular

---

## Small

12px

Regular

---

# Font Weights

Regular

400

Medium

500

SemiBold

600

Bold

700

---

# Spacing System

Base Unit

8px

Spacing Scale

4

8

12

16

24

32

40

48

64

Usage

Padding

Margins

Grid

Cards

Buttons

---

# Border Radius

Small

8px

Medium

12px

Large

16px

Extra Large

24px

Floating Action Button

28px

---

# Elevation

Level 1

Cards

2dp

---

Level 2

Dialogs

4dp

---

Level 3

Bottom Sheet

8dp

---

Level 4

Floating Action Button

12dp

---

# Icon Sizes

Small

16px

Medium

24px

Large

32px

Extra Large

48px

---

# Button Sizes

Height

52px

Corner Radius

16px

Minimum Width

120px

Padding

16px

---

# Input Fields

Height

56px

Border Radius

16px

Internal Padding

16px

---

# Card Sizes

Padding

20px

Radius

20px

Gap Between Cards

16px

---

# Bottom Navigation

Height

72px

Icon Size

24px

Label Size

12px

Floating Button Diameter

64px

---

# Charts

Corner Radius

12px

Animation Duration

500ms

Chart Padding

16px

---

# Animation Tokens

Fast

150ms

Medium

300ms

Slow

500ms

Premium

700ms

---

# Signature Animation

Expense Added

Button Compress

↓

Coin Flip

↓

Coin Drop

↓

Wallet Bounce

↓

Dashboard Refresh

↓

Budget Intelligence Update

↓

AI Insight Update

↓

Success Snackbar

Duration

700ms

---

# Shadows

Small

0 2 6

Medium

0 6 16

Large

0 10 30

Opacity

10%

---

# Grid System

Mobile Width

360–430px

Columns

4

Margin

16px

Gutter

16px

---

# Accessibility

Minimum Touch Area

48x48

Minimum Contrast

WCAG AA

Dynamic Text

Supported

Screen Reader

Supported

---

# Responsive Rules

Phone

Primary Target

Tablet

Stretch Cards

Web

Future Version

---

# Flutter Mapping

colors.dart

app_theme.dart

text_styles.dart

spacing.dart

dimensions.dart

animations.dart

icons.dart

constants.dart

---

# Versioning Rules

Design Tokens should never be hardcoded inside widgets.

Every value must come from the centralized design token library.

---

# CEO Vision

Design consistency builds trust.

Users may not consciously notice consistent spacing, typography, or animation—but they immediately notice when those elements are inconsistent.

Every screen should feel like it belongs to the same product, regardless of who designed or developed it.
