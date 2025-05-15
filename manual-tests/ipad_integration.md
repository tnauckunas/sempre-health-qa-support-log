# iPad Integration Test Log – Sempre Health  
**Engineer:** Tomas Nauckunas  
**Scope:** iPad Setup, OS Validation, App Installation, Device Sync  
**Duration:** 2020–2022

---

## 🔍 Purpose

To validate the seamless integration between Sempre Health devices and iPads issued to patients for remote monitoring. This includes firmware compatibility, app installation success, Bluetooth handshake, and data visualization within the patient dashboard.

---

## 📱 Test Devices Used

| Device        | OS Version     | Notes                          |
|---------------|----------------|---------------------------------|
| iPad Mini     | iPadOS 13.4     | Original rollout, base support |
| iPad Air 2    | iPadOS 14.2     | Required manual patching       |
| iPad (Gen 6)  | iPadOS 15.3     | Used for later batch testing    |
| iPad (Gen 7)  | iPadOS 15.5     | Smoothest integration recorded  |

---

## ✅ Validation Checklist

- [x] iPad fully charged  
- [x] Updated to latest iPadOS via OTA  
- [x] Sempre App installed via App Store or TestFlight  
- [x] Device successfully paired via Bluetooth  
- [x] Device auto-detected by app on launch  
- [x] Measurement simulation triggers dashboard update  
- [x] Data visible in patient view within 5 seconds  
- [x] Device retains connection after app is backgrounded  
- [x] Location services + permissions validated

---

## ❌ Common Integration Issues Found

| Issue | Description | Resolution |
|-------|-------------|------------|
| App crash on launch | Happened on iPadOS 14.1 | Reinstalled, confirmed fixed in app v2.3 |
| Dashboard data delay | Sync >10s on Gen 6 | Re-paired device, confirmed battery lag |
| Bluetooth not auto-connecting | iPad didn’t retain pairing | Removed old connections, rebooted device |
| Incomplete setup on TestFlight build | App stuck on “Searching...” | Cleared TestFlight cache, reinstalled |

---

## 🔁 Post-Test Actions

- Flagged iPadOS 14.1 as unreliable for rollout  
- Created pre-deployment checklist to include:
  - OS version audit  
  - Bluetooth pairing confirmation  
  - App version consistency  
  - Patient dashboard test  
- Helped define SOP for field techs handling iPad kits

---

## 🧠 Lessons Learned

- iOS updates often break integration in subtle ways — don’t trust it without testing  
- Apps must be tested **freshly installed**, not just “opened again”  
- Always test **battery % + permissions** as invisible blockers  
- Consistency between app version and firmware is critical to sync

---

## 📅 Last Updated: May 2025
