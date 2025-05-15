# Device Failure Log – Sempre Health  
**Engineer:** Tomas Nauckunas  
**Time Period Covered:** 2020–2022  
**Context:** Devices tested, returned, or flagged during field support / QA setup phase.

---

## 📋 Purpose

This log summarizes real-world device failures discovered during setup, testing, or deployment preparation for Bluetooth-integrated medical kits. These records helped refine test protocols, predict systemic issues, and guide engineering feedback.

---

## 🚨 Critical Failures Logged

| Date       | Device ID | Issue Summary                          | Resolution Summary                      | Notes |
|------------|-----------|----------------------------------------|------------------------------------------|-------|
| 2020-11-12 | #SH1042   | Power button non-responsive            | Replaced unit – confirmed internal board fault | No LED flash during boot |
| 2021-02-08 | #SH2188   | Repeated Bluetooth drop after pairing | Updated firmware, issue persisted → RMA | Affected 3 devices in same batch |
| 2021-05-26 | #SH3311   | Data not syncing to iPad dashboard     | Reinstalled app, reset device → success | App showed device paired, but no data until re-login |
| 2021-09-13 | #SH4127   | Random shutdown during active use      | Battery test failed → flagged + pulled  | Logged voltage drop on charge cable |
| 2022-01-03 | #SH5276   | Joystick input ghosting                | Replaced peripheral – issue fixed       | Suspected EMI interference in charger location |

---

## ⚠️ Patterns Identified

- Firmware version **v3.9.1** correlated with 40% of sync issues  
- Devices with **factory battery voltage <3.4V** had higher failure risk  
- Joysticks from Batch #A47 showed input lag or ghosting across multiple iPads

---

## 🛠️ Preventative Actions Taken

- Flagged weak firmware version to QA leadership  
- Added battery voltage check to pre-deployment checklist  
- Recommended joystick testing be separated from charger testing to isolate variables  
- Suggested integration of pairing diagnostics inside app UI

---

## 🧠 QA Lessons Learned

- Field logs must include: **device ID**, **symptoms**, **attempted fixes**, and **environmental notes**  
- QA isn’t about finding *any* problem — it’s about tracking which ones **repeat**  
- Logging physical + behavioral failures = better engineer feedback and faster issue resolution

---

## 📅 Last Updated: May 2025

