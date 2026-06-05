# Incubyte – Gmail Compose Manual Testing Assessment

> **Role:** Senior QA Test Craftsperson  
> **Submitted by:** Avinash chaudhary  
> **Date:** June 2025  
> **Platform under test:** Gmail (https://mail.google.com) – Compose Feature

---

## 1. Assignment Objective

Demonstrate comprehensive manual test design skills by creating a professional test suite for the **Gmail Compose** functionality covering the following specific test data:

| Field   | Value                   |
|---------|-------------------------|
| Subject | `Incubyte`              |
| Body    | `QA test for Incubyte`  |

---

## 2. Scope

### In Scope
- Gmail Compose window (open, minimise, maximise, pop-out)
- Recipient field validation (To, CC, BCC) — single and multiple recipients
- Subject and Body field validation
- Email send (button click & keyboard shortcut)
- Draft auto-save, recovery, and reopen
- Attachment handling (standard and boundary-size files)
- Reply and Forward workflows
- Keyboard / Tab navigation (usability)
- Network resilience and recovery behaviour
- Browser crash / refresh recovery (reliability)
- Boundary conditions on subject length, body size, recipient count, attachment size

### Out of Scope
- Gmail account creation / registration
- Gmail Settings configuration
- Gmail Labels and Filters
- Gmail API / backend testing
- Performance / Load testing
- Mobile application (Android / iOS) – separate test suite required
- Accessibility (WCAG compliance) – flagged for future sprint

---

## 3. Test Design Approach

This test suite follows a **risk-based, layered test design** approach:

| Technique | Application |
|-----------|-------------|
| **Equivalence Partitioning** | Valid/Invalid email formats; body sizes (small, medium, large) |
| **Boundary Value Analysis** | Subject length limits, attachment size limits, recipient count |
| **State Transition Testing** | Compose window states: Open → Minimised → Maximised → Closed |
| **Error Guessing** | Blank fields, malformed addresses, network disruptions, browser crash |
| **Decision Table Testing** | Combinations of To / CC / BCC populated vs empty |
| **Use Case Testing** | End-to-end send, reply, forward, draft workflows |

---

## 4. Test Coverage Summary

| Category | Count |
|----------|-------|
| Positive Test Cases | 22 |
| Negative Test Cases | 13 |
| Boundary Test Cases | 6 |
| Usability Test Cases | 4 |
| Reliability Test Cases | 4 |
| **Total Traditional TCs** | **49** |
| BDD Scenarios (Gherkin) | 18 |
| **Grand Total** | **67** |

---

## 5. Types of Testing Included

- **Functional Testing** – Core compose, send, reply, forward flows
- **Negative / Validation Testing** – Invalid inputs, blank fields, oversized attachments
- **Boundary Value Testing** – Edge cases at min/max limits
- **Usability Testing** – Keyboard navigation, tab order, window states
- **Reliability Testing** – Network resilience, draft recovery, multi-window
- **BDD / Acceptance Testing** – Gherkin-syntax scenarios for stakeholder communication

---

## 6. Repository Structure

```
Incubyte-Gmail-Manual-Assessment/
│
├── Test_Cases/
│   └── Gmail_Compose_Test_Cases.xlsx      ← Traditional test cases (49 TCs, 2 sheets)
│
├── BDD/
│   └── Gmail_Compose_BDD_Test_Cases.xlsx  ← Gherkin BDD scenarios (18 scenarios)
│
├── Assumptions/
│   └── Assumptions.md                     ← Documented test assumptions
│
├── Screenshots/
│   └── sample_execution.png               ← Sample test execution evidence
│
└── README.md                              ← This file
```

---

## 7. Assumptions

See [`Assumptions/Assumptions.md`](Assumptions/Assumptions.md) for the full list.

Key assumptions at a glance:

- Tester has access to a valid, active Gmail account
- Internet connectivity is stable unless a test explicitly simulates disruption
- The recipient email address used in positive tests (`tester@example.com`) is valid and active
- Gmail service is available and not undergoing maintenance
- Browser is a latest stable version of Chrome, Firefox, or Edge
- Gmail keyboard shortcuts are enabled in Gmail Settings for keyboard shortcut tests

---

## 8. Deliverables

| # | Deliverable | File |
|---|-------------|------|
| 1 | Traditional Style Test Cases (49 TCs) | `Test_Cases/Gmail_Compose_Test_Cases.xlsx` |
| 2 | BDD Gherkin Test Cases (18 scenarios) | `BDD/Gmail_Compose_BDD_Test_Cases.xlsx` |
| 3 | Test Assumptions | `Assumptions/Assumptions.md` |
| 4 | Execution Evidence | `Screenshots/sample_execution.png` |
| 5 | This README | `README.md` |

---

## 9. Excel File Guide

### Traditional Test Cases — Column Reference

| Column | Description |
|--------|-------------|
| TC ID | Unique identifier (TC_001 … TC_049) |
| Module | Sub-feature under test |
| Test Scenario | Clear, one-line description of what is being tested |
| Preconditions | State required before test execution begins |
| Steps to Reproduce | Full end-to-end steps (each TC starts from Gmail login) |
| Test Data | Specific data inputs used |
| Expected Result | Precisely defined, observable outcome |
| Priority | High / Medium / Low |
| Type | Positive / Negative / Boundary / Usability / Reliability |

### BDD Test Cases — Column Reference

| Column | Description |
|--------|-------------|
| Scenario ID | Unique identifier (BDD_001 … BDD_018) |
| Feature | High-level feature grouping |
| Scenario Title | Human-readable scenario name |
| Given | Precondition / system state |
| When | User action(s) |
| Then | Expected observable outcome |
| Priority | High / Medium / Low |
| Type | Maps to testing type |

---

## 10. Risk Register

| Risk | Likelihood | Impact | Mitigation |
|------|------------|--------|------------|
| Gmail UI changes invalidate steps | Medium | High | Screenshots taken at time of test design; update steps per release |
| Free Gmail account sending limits (500/day) | Low | Medium | Use a dedicated test account |
| Auto-draft save timing varies by network speed | Medium | Low | Extend wait time in steps to 10 seconds for slow connections |
| BCC visibility behaviour differs from documented | Low | Medium | Document actual vs expected and raise as defect |

---

*This test suite was designed to reflect the standards expected of a Senior QA Test Craftsperson and is ready for direct upload to GitHub and submission to Incubyte.*
