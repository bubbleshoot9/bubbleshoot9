# 🐛 Defect Report Template  
## Gen AI–Enhanced Root Cause Analysis

---

## 🧾 Defect Metadata
- **Defect ID:** DEF-2025-001  
- **Priority / Severity:** 🔴 Critical / 🔴 Blocker  
- **Status:** New / In Progress / Fixed / Retest / Closed  
- **Reported By:** [QA Name]  
- **Assigned To:** [Dev Name]  
- **Version / Sprint:** v2.5.0 / Sprint 23  
- **Environment:** Prod / Staging / QA / Local  

---

## 📋 Summary
**One-line description of the issue**  
> *Example:* Password reset fails for emails containing `+`

---

## 📝 Description

**Expected:**  
System accepts RFC-compliant emails and sends reset email.

**Actual:**  
400 Bad Request returned; no reset email sent.

---

## 🔁 Steps to Reproduce
1. Go to `/forgot-password`  
2. Enter `user+test@example.com`  
3. Submit request  
4. Observe error  

- **Repro:** 100%  
- **Browsers/Devices:** Chrome, Firefox, Safari | Desktop, iOS  

---

## 🖼️ Evidence
- Screenshots (UI + Network tab)  
- Short video (optional)  
- Logs / stack traces

---

## 🔍 Root Cause Analysis (Human)
- **Cause:** Email validation regex excludes `+`  
- **Location:** `emailValidator.ts`  
- **Fix:** Update regex to support RFC 5322

---

## 🤖 Gen AI–Assisted RCA (Accelerator)

**AI Findings (Reviewed):**
- Regex not RFC-compliant  
- Suggested broader regex  
- Identified additional edge cases  
- Flagged potential injection risks  

**Human Validation:**  
✅ Root cause confirmed  
✅ Fix approved  
⚠️ Security testing required  

---

## 🛠️ Actions

**Immediate**
- [ ] Update regex  
- [ ] Add unit tests  
- [ ] Deploy to staging  

**QA**
- [ ] Retest fix  
- [ ] Execute edge cases  
- [ ] Run security checks  

**Long-Term**
- [ ] Replace custom regex with standard library  
- [ ] Add monitoring for validation failures  

---

## 📊 Impact

| Area | Impact |
|---|---|
| User | 🔴 High |
| Business | 🟠 Medium |
| Tech Risk | 🟡 Low |
| Security | 🟡 Medium |

---

## 🔗 References
- User Story / Epic  
- Related Defects  
- RFC / Internal Docs  

---

## 💬 Comments
Short, time-stamped discussion between Dev / QA / Product.

---

> **Principle:**  
> Clear defects save time.  
> Gen AI accelerates insight.  
> Humans own decisions.
