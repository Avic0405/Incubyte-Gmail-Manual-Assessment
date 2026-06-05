# Test Assumptions – Gmail Compose | Incubyte QA Assessment

> Document Version: 1.0  
> Date: June 2025  
> Author: Avinash chaudhary

---

## Purpose

This document records all assumptions made during the design and execution of the Gmail Compose manual test suite. These assumptions define the boundaries and preconditions that are taken as true unless explicitly contradicted in a specific test case.

---

## Environment Assumptions

| # | Assumption |
|---|------------|
| ENV-01 | The application under test is the web-based Gmail client accessed at `https://mail.google.com` |
| ENV-02 | Testing is performed on a desktop or laptop computer (not a mobile device or tablet) |
| ENV-03 | The browser in use is a **latest stable version** of Google Chrome, Mozilla Firefox, or Microsoft Edge |
| ENV-04 | The operating system is Windows 10/11, macOS 12+, or Ubuntu 20.04+ |
| ENV-05 | The screen resolution is at minimum **1366 × 768** |
| ENV-06 | The tester's system clock and timezone are set correctly |

---

## Account and Access Assumptions

| # | Assumption |
|---|------------|
| ACC-01 | The tester has access to a **valid, active Google / Gmail account** with no restrictions |
| ACC-02 | The Gmail account is **not suspended**, **not flagged for spam**, and **not pending verification** |
| ACC-03 | The Gmail account has **not exceeded** its daily sending limit (500 emails/day for free accounts) |
| ACC-04 | Two-factor authentication (2FA), if enabled, is set up and accessible (authenticator app or phone) |
| ACC-05 | The tester has the login credentials (email and password) ready prior to test execution |
| ACC-06 | The account has the default Gmail interface (not a G Suite / Google Workspace managed account with custom restrictions unless specified) |

---

## Recipient and Network Assumptions

| # | Assumption |
|---|------------|
| NET-01 | A **stable internet connection** is available for all tests unless the test explicitly simulates a network interruption |
| NET-02 | The **recipient email address** used in positive test cases (`tester@example.com` or equivalent) is valid, active, and capable of receiving emails |
| NET-03 | The recipient's mailbox is **not full** and will accept incoming messages |
| NET-04 | Gmail's mail servers and services are **available and operational** during test execution (no planned maintenance or known outages) |
| NET-05 | DNS resolution for `mail.google.com` is functioning correctly |

---

## Gmail Feature and Configuration Assumptions

| # | Assumption |
|---|------------|
| CFG-01 | **Gmail keyboard shortcuts are enabled** in Gmail Settings (Settings → See all settings → General → Keyboard shortcuts: ON). This applies specifically to tests TC_011, TC_017, and BDD_009 |
| CFG-02 | The default Gmail theme and interface layout is in use (no custom modifications that would rearrange Compose elements) |
| CFG-03 | The Gmail **Compose** button is visible in the left navigation panel |
| CFG-04 | Gmail's **auto-save draft** feature is active (enabled by default; not manually disabled via third-party extensions) |
| CFG-05 | No browser extensions (e.g., ad-blockers, privacy blockers) interfere with Gmail's compose functionality |
| CFG-06 | The tester's Gmail account has **not blocked the recipient** for tests that verify blocking behaviour |
| CFG-07 | Gmail's **spam filter** does not intercept test emails sent between tester-controlled accounts |

---

## Test Data Assumptions

| # | Assumption |
|---|------------|
| DAT-01 | The subject `Incubyte` and body `QA test for Incubyte` are treated as the **canonical test data** for all primary positive test cases |
| DAT-02 | Attachment files referenced in boundary tests (e.g., 25MB file, 30MB file) will be **prepared by the tester** prior to execution |
| DAT-03 | The 250-character subject string used in boundary tests will be pre-composed and available for paste |
| DAT-04 | For multiple-recipient tests, **all email addresses listed** are valid and available to the tester |
| DAT-05 | A previously received email exists in the inbox for Reply and Forward test cases |

---

## Scope Exclusions (Assumed Out of Scope)

| # | Excluded Area | Rationale |
|---|---------------|-----------|
| EX-01 | Gmail mobile app (Android / iOS) | Separate UI and test scope |
| EX-02 | Gmail API / programmatic access | Backend / integration concern |
| EX-03 | Accessibility (screen reader, WCAG 2.1) | Flagged for dedicated accessibility testing sprint |
| EX-04 | Performance / load testing | Requires specialised tooling (JMeter, Locust) |
| EX-05 | Gmail account creation, deletion, or settings management | Out of compose feature scope |
| EX-06 | Google Workspace (G Suite) enterprise features | Free consumer Gmail only |

---

## Defect Logging Assumptions

| # | Assumption |
|---|------------|
| DEF-01 | Any deviation between actual and expected result will be logged as a defect in the project's issue tracker with reproduction steps, priority, and severity |
| DEF-02 | A defect severity scale of **Critical / High / Medium / Low** will be applied |
| DEF-03 | Screenshots or screen recordings will be captured for every defect found |

---

*These assumptions should be reviewed and agreed with the project stakeholders before test execution begins. Any assumption found to be invalid should be updated here and the affected test cases revised accordingly.*
