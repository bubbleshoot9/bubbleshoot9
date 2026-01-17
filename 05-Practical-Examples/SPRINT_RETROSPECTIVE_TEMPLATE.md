# 🔁 Sprint Retrospective Template  
## Quality-Focused: What Worked, What Didn't, What's Next

---

## Sprint Overview

**Sprint Number:** 23  
**Sprint Goal:** Implement MFA feature and improve test automation coverage  
**Duration:** 2 weeks (Dec 16 – Dec 30, 2025)  
**Team:** 5 Developers, 3 QA, 1 Product Owner, 1 Scrum Master  

---

## 📊 Sprint Metrics

| Metric | Target | Actual | Status |
|------|------|------|------|
| **Stories Completed** | 8 | 7 | 🟡 87% |
| **Defects Found (Pre-Prod)** | N/A | 12 | ✅ Caught early |
| **Defects Escaped to Prod** | 0 | 1 | 🔴 RCA required |
| **Automation Coverage** | +10% | +12% | ✅ Exceeded |
| **Manual Test Hours** | 40 hrs | 35 hrs | ✅ GenAI assisted |
| **Sprint Velocity** | 34 pts | 31 pts | 🟡 Slightly below |

---

## ✅ What Went Well

### 1️⃣ GenAI Test Design Acceleration
**What:** LLM-generated Gherkin scenarios from user stories  
**Impact:** Test design reduced by ~50% (2 hrs → 15 mins per story)  

> *“The AI-generated MFA edge cases were spot-on—we caught 3 defects early.”*  
> — Alice (Senior QA)

**Action:** Expand GenAI usage; train mid-level QA on prompt engineering

---

### 2️⃣ Three Amigos Collaboration
**What:** Three Amigos held for all 7 stories pre-sprint  
**Impact:** Zero scope creep; fewer clarifications during dev  

> *“QA input early helped us design for edge cases, not retrofit later.”*  
> — Dev Lead

**Action:** Add Three Amigos to **Definition of Ready**

---

### 3️⃣ Blameless RCA
**What:** Blameless RCA for escaped email validation defect  
**Impact:** Process improvement identified; morale preserved  

> *“AI-assisted RCA kept us focused on fixing systems, not blaming people.”*  
> — Product Manager

**Action:** Continue GenAI-assisted RCA adoption

---

## ❌ What Didn’t Go Well

### 1️⃣ Escaped Defect (Email Validation)
**What:** `+` symbol rejected in email field  
**Root Causes:**
- Automation covered happy paths only  
- Manual testing assumed automation coverage  
- RBT matrix didn’t flag validation logic as risky  

**Impact:** 3 support tickets; ~2% users affected  

**Actions:**
- [ ] Update RBT matrix (email validation → medium risk)  
- [ ] Expand automated email data (GenAI-generated edge cases)  
- [ ] Add validation checks to exploratory charters  

---

### 2️⃣ Flaky Automation Tests
**What:** 4 intermittent Playwright failures in CI  

**Root Causes:**
- BrowserStack network latency  
- Missing explicit waits  
- No retry strategy  

**Impact:** 6 false positives; pipeline delays  

**Actions:**
- [ ] Introduce intelligent waits / self-healing  
- [ ] Add retry logic (max 3) for network-dependent tests  
- [ ] Pair review of Playwright waits  

---

### 3️⃣ Manual Testing Bottleneck
**What:** Manual regression still took 35 hours  

**Root Causes:**
- 40% regression still manual  
- Automation coverage at 60%  
- Unplanned tester absence  

**Impact:** QA sign-off delayed by 1 day  

**Actions:**
- [ ] Automate top 10 most-run manual tests (RBT-driven)  
- [ ] Enable dev-led smoke tests (shift-left)  
- [ ] Improve test coverage resilience  

---

## 💡 Ideas & Experiments

### 🧪 GenAI Exploratory Charters (Pilot)
**Goal:** Increase edge-case discovery by 20%  
**Owner:** Alice  
**Timeline:** Sprint 24 pilot → Sprint 25 review  

### 🎨 Visual Regression Testing
**Goal:** Catch theme/Dark Mode regressions  
**Tooling:** Playwright + Percy  
**Owner:** Bob  
**Timeline:** Sprint 24 POC  

### 🔁 Shift-Left Dev Smoke Tests
**Goal:** Catch defects earlier  
**Owner:** Dev Lead + QA Lead  
**Timeline:** Training Sprint 24; mandatory Sprint 25  

---

## 🎯 Action Items (Next Sprint)

| Action | Owner | Priority | Due |
|------|------|------|------|
| Update RBT matrix | QA Lead | 🔴 High | Sprint 24 Day 1 |
| Fix flaky Playwright tests | Bob (QA) | 🔴 High | Sprint 24 Day 3 |
| Automate top 10 manual tests | Dev + QA | 🟠 Medium | Sprint 24 End |
| GenAI exploratory pilot | Alice | 🟡 Low | Sprint 24 End |
| Dev smoke test training | Dev Lead | 🟠 Medium | Sprint 24 Day 5 |
| Visual regression POC | Bob | 🟡 Low | Sprint 25 |

---

## 📈 Quality Trends (Last 3 Sprints)

| Sprint | Escaped Defects | Pre-Prod Defects | Automation % | Manual Hours |
|------|------|------|------|------|
| **21** | 2 | 8 | 50% | 45 |
| **22** | 1 | 10 | 58% | 42 |
| **23** | 1 | 12 | 62% | 35 |

**Trends**
- ✅ Shift-left improving (pre-prod defects ↑)  
- ✅ Automation coverage increasing  
- ✅ Manual effort decreasing  
- 🔴 Escaped defects stable → RBT refinement needed  

---

## 🗣️ Team Feedback (Anonymous)

**Energising**
- “GenAI made test design fast and enjoyable”
- “Blameless RCA felt safe”
- “Three Amigos improved collaboration”

**Draining**
- “Flaky tests waste time”
- “Manual regression still repetitive”
- “Production defect was stressful”

**Improve Next Sprint**
- “Fix flaky tests first”
- “Automate high-frequency manual tests”
- “More GenAI training”

---

## 🎓 Team Shout-Outs

🏆 **Alice (Senior QA):** Led GenAI pilot; caught 3 defects  
🏆 **Dev Lead:** Drove Three Amigos adoption  
🏆 **Bob (QA):** Identified flaky test root causes  
🏆 **Product Manager:** Championed blameless culture  

---

## 🔑 Key Takeaways

✅ Shift-left delivering value  
✅ GenAI accelerating design & execution  
⚠️ Validation coverage gaps remain  
⚠️ Flaky tests erode trust  

**Next Sprint Focus**
1. Stabilise automation  
2. Reduce manual bottlenecks  
3. Strengthen RBT  
4. Expand GenAI experimentation  

---

**Facilitator:** Scrum Master  
**Date:** 30 Dec 2025  
**Next Retro:** Sprint 24 (13 Jan 2026)

---

**Philosophy:** Retrospectives drive learning, not blame. Improve systems, experiment safely, and celebrate progress.
