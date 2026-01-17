# 🎭 QA Cultural Rituals & Best Practices

> **Philosophy:** A framework only succeeds if the culture sustains it. These rituals turn engineering standards into *living behaviours*, not static documents.

---

## 🐣 1. “Pay It Forward” Onboarding (Self-Healing Docs)

**Practice:** Every new starter becomes the temporary owner of onboarding documentation for their first 30 days.

- **The Expectation:** Identify at least:
  - One missing step  
  - One outdated instruction  
  - One broken or unclear link in the Onboarding Starter Kit  
- **The Commitment:** Before the end of month one, submit a PR improving the onboarding flow for the *next* joiner  
- **Outcome:**  
  - Documentation that never rots  
  - Immediate ownership mindset  
  - New starters contributing value from week one  

> Onboarding is not consumed—it is improved.

---

## 🛡️ 2. “Bug Bounty” for Technical Debt

**Practice:** Dedicated time for quality investment—either one full day per month or a fixed percentage of every sprint.

- **Focus Areas (No New Features):**
  - Reducing the Toil Ratio  
  - Refactoring brittle Playwright / Selenium selectors  
  - Improving API mocks and test data strategies  
- **Outcome:**  
  - Automation debt is actively paid down  
  - Framework reliability improves sprint over sprint  
  - ROI remains demonstrably positive  

> Technical debt is treated as a visible risk, not background noise.

---

## 🧪 3. “Shadow-the-Dev” Days

**Practice:** Once per quarter, SDETs spend a full day pairing with a Developer—observing local builds, debugging, and workflows.

- **Primary Goal:** Understand real Developer Experience (DX)  
- **Non-Negotiable Insight:**  
  - If the automation suite is too slow or painful for developers to run locally, it must be optimised  
- **Actionable Outcomes:**  
  - Sharding strategies  
  - Faster feedback loops  
  - Better alignment between test design and dev reality  

> If developers can’t run it, it’s not production-grade automation.

---

## 📣 4. “Three Amigos” Is Mandatory

**Practice:** No ticket moves from *To Do* to *In Progress* without a short sync between Dev, QA, and Product.

- **Timebox:** 10 minutes  
- **Required Outputs:**  
  - Clear Definition of Done (DoD)  
  - Agreed Risk-Based Testing (RBT) priority  
- **Outcome:**  
  - Near-zero ambiguity  
  - Dramatic reduction in requirement-driven defects  

> Speed comes from clarity, not heroics.

---

## 🧹 5. “Clean-As-You-Go” Data Policy

**Practice:** Tests must be self-contained and environment-safe.

- **Rule:** No test may depend on pre-existing state  
- **Standard:**  
  - If a test creates data (e.g. a user via API), it must clean up in an `afterAll` hook or fixture  
- **Outcome:**  
  - Reliable parallel execution  
  - Stable shared environments  
  - No “test pollution” over time  

> Every test owns its own birth and its own death.

---

These rituals are enforced socially before they are enforced technically—because culture scales faster than rules.
