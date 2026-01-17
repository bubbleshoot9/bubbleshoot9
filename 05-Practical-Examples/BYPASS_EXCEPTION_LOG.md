### 🚨 Exception Entry — #2025-04

- **Date:** 12 Oct 2025  
- **Affected Release:** Hotfix v2.4.1 — *Login Service*  
- **Quality Gate Bypassed:** Gate 3 — Full Automation Regression Suite  

---

#### 📌 Business Justification
A **P0 production incident** resulted in login failure for **100% of Android users**.  
Estimated revenue impact was **~£12k per hour**, making immediate release critical to limit business loss.

---

#### ⚠️ Risk Assessment
- **Overall Risk:** High  
- **Known Exposure:** Potential regression in the *Sign-up* flow due to shared authentication modules.

---

#### 🛡️ Mitigation Plan
To offset the bypassed gate, the following controls were enacted:

1. **Pre-Deploy Validation**
   - Manual smoke testing of the *Sign-up* flow completed on **two physical Android devices**.

2. **Post-Deploy Automation**
   - Full automation regression suite scheduled to run at **02:00 AM** post-deployment.

3. **Day-After Assurance**
   - Dedicated manual QA verification scheduled for **09:00 AM** the following day.

> Risk was consciously accepted with layered safeguards in place to detect and correct any regression rapidly.

---

#### ✅ Approval
- **Chad Shaw** — Test Manager  
- **Peter Jones** — Product Owner  

---

> *Exception approved under emergency release protocol. This entry is logged for audit and retrospective review.*
