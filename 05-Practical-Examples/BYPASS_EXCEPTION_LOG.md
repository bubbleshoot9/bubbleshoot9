### 🚨 Exception Entry — #2025-04

- **Date:** 12 Oct 2025  
- **Release:** Hotfix v2.4.1 — Login Service  
- **Gate Bypassed:** Gate 3 (Full Automation Regression)  

- **Justification:** P0 incident—login failure affecting 100% of Android users (~£12k revenue loss per hour).  
- **Risk:** High—possible regression in shared Sign-up auth flow.  

- **Mitigation:**  
  1. Manual Sign-up smoke test on two physical devices  
  2. Full regression scheduled for 02:00 AM post-deploy  
  3. Manual verification at 09:00 AM next day  

- **Approved By:** Chad Shaw (QA Lead), Peter J. (Product Owner)
