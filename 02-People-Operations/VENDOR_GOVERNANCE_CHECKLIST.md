# 🤝 Vendor & Offshore Governance Checklist

> **Purpose:** Ensure external partners (SIs / Managed Services) operate at full technical parity with internal teams—delivering quality, transparency, and measurable ROI.

This checklist is used for **vendor onboarding, quarterly health checks, and renewal decisions**.

---

## 🏗️ 1. Technical Integration & Standards

*Before a single line of automation is written, vendors must demonstrate full alignment with internal engineering standards.*

- [ ] **Environment Parity**  
  Vendor engineers have access to the same CI/CD pipelines, repositories, and Dockerised environments as internal teams.

- [ ] **Code Quality Gates**  
  All vendor PRs are subject to identical automation review standards and approval workflows.

- [ ] **Technical Debt Ownership**  
  Vendor-owned code must be refactored and maintained by the vendor.  
  **Target:** < 10% of sprint capacity spent on vendor-created debt.

- [ ] **Tooling Alignment**  
  Vendor uses the approved automation stack (e.g. Playwright, REST tooling).  
  No proprietary or black-box frameworks without explicit approval.

> Vendors extend capability—not introduce parallel standards.

---

## 📈 2. Delivery & Metric Accountability

*Vendors are measured using the same outcome-based metrics as internal teams.*

- [ ] **Defect Rejection Rate**  
  Fewer than 5% of vendor-raised defects are rejected as “Not a Bug” or “Invalid”.

- [ ] **Automation Coverage**  
  Vendor automates > 80% of features they are assigned to validate.

- [ ] **SLA Compliance**  
  P0 / P1 defects are triaged within the agreed SLA (typically ≤ 4 hours).

- [ ] **Outcome-Based Billing**  
  Commercial models are tied to deliverables (e.g. “Feature Automation Complete”), not hours logged.

> Velocity without quality is noise. These metrics keep it honest.

---

## 🧠 3. Knowledge Retention & Security

*Protecting intellectual property while keeping the bus factor low.*

- [ ] **Bi-Weekly Technical Demos**  
  Vendors regularly walk internal leads through framework changes and contributions.

- [ ] **Living Documentation**  
  READMEs, diagrams, and Confluence pages are updated continuously—not at project end.

- [ ] **Security & Compliance Training**  
  All vendor staff complete domain-relevant PII / GDPR / security training before access is granted.

- [ ] **Offboarding Protocol**  
  A complete Knowledge Transfer (KT) pack exists for every contractor or team roll-off.

> Knowledge must stay after people leave.

---

## 🏆 4. “One Team” Culture Check

*We do not operate a two-tier engineering model.*

- [ ] **Ceremony Participation**  
  Vendors attend Sprint Planning, Reviews, and Retrospectives as peers—not order takers.

- [ ] **Equal Recognition**  
  High-performing vendor engineers are recognised in the same forums as internal team members.

> Culture drift is an early warning signal—this section catches it early.

---

## ✅ Governance Outcome

A vendor is considered **Healthy** only if all four sections remain green.  
Any sustained red area triggers a **remediation plan or exit decision**.

This checklist ensures partners scale quality—never dilute it.
