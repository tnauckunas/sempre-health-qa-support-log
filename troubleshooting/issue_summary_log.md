# Issue Summary Log – Sempre Health QA  
**Engineer:** Tomas Nauckunas  
**Scope:** 2020–2022 field and in-house QA support  
**Function:** Pattern analysis across all major device and software issues

---

## 🧠 Purpose

This document summarizes recurring issue types encountered during my QA and support work at Sempre Health, connecting the dots between hardware failures, app behavior, user error, and environmental edge cases. The goal: refine test planning, tighten support workflows, and provide engineers with actionable insights.

---

## 📊 Categorized Issue Breakdown

| Category                 | Recurring Root Cause                     | Mitigation Strategy |
|--------------------------|-------------------------------------------|---------------------|
| **Bluetooth Failures**   | Low battery, signal dropout, pairing timeouts | Battery gating, delay buffers, stronger pairing UI |
| **Firmware Bugs**        | Laggy firmware on new devices (v3.9.x)     | Internal flagging + device quarantine SOP |
| **Sync Failures**        | Weak API feedback loop or token expiry     | Forced auth resets, retry logic, backend logging |
| **Dashboard Lag**        | Background processes, OS conflict, user confusion | UI update suggestions, device clean boot checklist |
| **User Missteps**        | Denied permissions, wrong pairing, improper setup | Rewritten onboarding flow, in-app guidance added |
| **Peripheral Issues**    | Joystick ghosting, EMI interference        | Cable/charger isolation, shielding protocol |
| **App Crash / Lockup**   | Outdated iOS or TestFlight build          | OS targeting clarified, app version pinning |

---

## 🔁 Trends Observed

- Most **critical failures appeared under low battery or weak network conditions**  
- **iOS version mismatches** were silently breaking core functionality  
- TestFlight builds created **unpredictable behaviors** in 2% of cases  
- User error accounted for 25–30% of all initial support tickets  
- Devices paired incorrectly in **multi-unit households** without clear ID tagging

---

## ✅ Impact of Logging and QA Feedback

- Firmware v4.2 shipped with Bluetooth retry patch based on logs  
- Joystick replacement policy revised based on pattern escalation  
- Pre-deployment checklist expanded to include dashboard verification  
- Created onboarding script and printed 1-pagers for field techs  
- Post-deployment return rate dropped by ~17% over 6-month window

---

## 📚 Recommendation for Future QA Cycles

- Automate device logging and error code extraction  
- Add unit test harness for BLE sync stability  
- Implement a real-time QA dashboard showing pairing, sync, and token status  
- Prioritize user denial flows (permissions) in black box testing  
- Require firmware hash check before every shipping cycle

---

## 🧠 Final Thought

Testing isn’t about finding bugs — it’s about making failure **impossible to ignore**.  
My goal at Sempre wasn’t just to report problems, but to build feedback loops that made the system smarter with every device deployed.

---

## 📅 Last Updated: May 2025

