# 🛡️ Quality Gates & Production Readiness Criteria
> **Standard:** TMMi Level 5 (Optimized) | **Strategic Focus:** Scalable Quality for 5:1 Dev-to-QA Ratios

Quality Gates are the **non-negotiable control points** within our CI/CD pipeline. They ensure that even with a lean QA function, no feature reaches production without meeting clearly defined, high-trust stability and risk standards.

---

### 🚪 Gate 1: Code Commit (Developer Level)
*Owner: Engineering Team | Tooling: Pre-commit hooks / Husky*

- [ ] **Linting:** Zero errors across TypeScript/Java codebases (ESLint / Checkstyle).
- [ ] **Unit Test Coverage:** Minimum **80% line coverage** for all newly introduced logic.
- [ ] **Shift-Left A11y:** Local `axe-core` accessibility checks completed for all modified UI components.

---

### 🚪 Gate 2: Pull Request (Peer & CI Level)
*Owner: GitHub Actions & Senior Engineers*

- [ ] **Peer Review:** At least one formal approval from a Senior Developer.
- [ ] **Smoke Suite:** Playwright/Appium `@smoke` tests must pass 100% on **Web & Mobile (BrowserStack)**.
- [ ] **Static Analysis:** No high-severity vulnerabilities detected via security scanning (Snyk / SonarQube).

---

### 🚪 Gate 3: Integration (The RBT Gate)
*Owner: 1 Automation Tester & 1 Manual Tester*

- [ ] **RBT Validation:** All **High-Risk features (Score 15–25)** must receive full manual exploratory sign-off.
- [ ] **Automation (AT):** All in-sprint automated coverage for **High and Medium Risk** features must be merged and passing.
- [ ] **Observability:** Error logging must be validated as *clear, meaningful, and actionable* (no generic or ambiguous error messages).

---

### 🤖 Automation Enforcement (Gate 3)

To ensure Gate 3 remains both effective and performant, we apply a **Tiered Automation Execution** model. Test execution is governed by metadata tags assigned during development based on the [RBT Score](./RBT_PRIORITY_MATRIX.md).

- **Mandatory Pass:** All tests tagged `@smoke` (critical path) must pass 100%.
- **Regression Requirement:** Tests tagged `@regression` (High / Medium Risk) must pass at **≥ 98%**.

---

### 🚪 Gate 4: Release Readiness (Leadership Level)
*Owner: Lead QA Consultant*

- [ ] **Defect Density:** Zero open *Critical* or *Major* defects.
- [ ] **The 10-Minute Rule:** Pipeline execution must complete in under 10 minutes to protect release velocity.
- [ ] **RCA Closure:** Any blockers carried over from the previous sprint must have a completed **Blameless RCA**.

---

### 🚪 Gate 5: Post-Deployment Monitoring (Live)
*Owner: QA Unit | Tooling: Playwright, New Relic / Sentry*

- [ ] **Synthetic Production Smoke:** Playwright smoke tests executed every 15 minutes in Production for core user flows (e.g. MFA, Login).
- [ ] **Real User Monitoring (RUM):** Live monitoring of JavaScript errors and performance via New Relic / Sentry.
- [ ] **Alerting:** Automated Slack alerts triggered for any Production Smoke failure.

---

> [!IMPORTANT]
> **The Hard Stop Rule:**  
> Any failure in **Gate 1 or Gate 2** automatically blocks merge.  
> Failures in **Gate 3 or Gate 4** require a formal *Risk Waiver* signed by both the Lead QA Consultant and the Product Owner.

---

### ⚖️ Emergency Override Protocol

In exceptional circumstances where a critical production hotfix is required and speed is the priority:

1. **Risk Evaluation:** Recalculate the [RBT Score](./RBT_PRIORITY_MATRIX.md).
2. **Post-Release Debt:** Schedule a mandatory *Regression Catch-up* within 24 hours of the hotfix.
3. **Audit Trail:** Document the bypass rationale during the next Sprint Retrospective.

---

## 📱 App Store Intelligence & Device Strategy

We treat the **Google Play Store** and **Apple App Store** as our most honest external QA signal.

- **Sentiment Analysis:** Weekly review of all ratings below 3 stars.
- **Evidence-Based Reproduction:** User-reported crashes are reproduced using the exact device and OS combination (e.g. Samsung S22 / Android 14) via the **Cloud Grid (BrowserStack)**.
- **Closing the Loop:** Every reproduced 1-star issue is logged as a High-Priority RCA to prevent recurrence.

---

## 📈 Strategic Resource Reinvestment

In a balanced delivery model, surplus capacity is not wasted on low-value testing. Instead, it is converted into **Technical Equity** that strengthens future delivery.

### When the [RBT Matrix](./RBT_PRIORITY_MATRIX.md) indicates Low Risk:

| Reinvestment Area | Activity |
| :--- | :--- |
| **Innovation Backlog** | Building AI-driven test data generators for developer use. |
| **Chaos Engineering** | Injecting controlled failures into API mocks to validate system resilience. |
| **Performance Budgets** | Baselining API response times to prevent gradual performance degradation. |
| **Framework Pruning** | Reducing CI/CD execution time to consistently meet the **10-Minute Rule**. |

---

### 🧠 Leadership Philosophy

These gates shift quality enforcement away from individuals and into the **delivery system itself**. This removes the need for reactive or policing behaviours and allows leadership to focus on coaching, enablement, and long-term capability building.

> *“We don’t wait for the next sprint to learn. By monitoring the App Store and running Production Smoke tests, we act as the **Voice of the Customer**. When workload is light, we invest—engineering the tools that ensure the next high-risk sprint moves faster and safer.”*
