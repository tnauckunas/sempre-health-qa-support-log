# Data Sync Issues – Sempre Health  
**Engineer:** Tomas Nauckunas  
**Role:** QA / Field Technician  
**Context:** Bluetooth medical device → iPad app → dashboard sync pipeline  
**Period:** 2020–2022

---

## Problem Statement

During QA validation and field setup, several devices failed to sync measurement data from the hardware to the Sempre Health iPad app or from the app to the patient dashboard. These failures were critical to flag early, as they directly impacted medical reporting.

---

## Sync Flow Observed

1. Measurement initiated on device  
2. Data sent via BLE to iPad  
3. Sempre app receives and logs data  
4. Data syncs with cloud (API push)  
5. Dashboard updates for user + backend access

---

## Common Failure Scenarios

| Stage Failed | Symptom | Root Cause | Resolution |
|--------------|---------|-------------|------------|
| BLE Transfer | No reading appears in app | Weak battery / pairing lost | Reboot + re-pair device |
| App Processing | App shows “connected” but no data appears | App stuck in stale state | Force close + reinstall |
| Cloud Sync | Data visible locally, not on dashboard | API call failed silently | Network reset + refresh |
| Post-Sync Update | Dashboard doesn’t show new measurement | Account mismatch or auth token expired | Relogin + clear local cache |

---

## Test Variations Run

- Simulated sync at 20%, 50%, and 80% battery  
- Switched iPads to test for local device vs app issue  
- Tested sync while on weak Wi-Fi and mobile hotspot  
- Compared sync times on iOS 14 vs 15  
- Re-ran tests with and without background apps open

---

## Key Findings

- Devices with <30% battery had 2× the sync failure rate  
- App versions pre-v2.4 had silent API timeout bugs  
- iPads running iOS 14.1 had longest sync delays  
- Users often misread “data received” as “data stored” — visual feedback was missing

---

## Fixes & Process Changes Suggested

- Add real-time sync status indicator in app (Success/Fail)  
- Force logout + re-auth if token error detected  
- Include battery check before sync attempt  
- Log BLE disconnects in app console for tech troubleshooting  
- Create field tech checklist for sync testing before deployment

---

## Lessons Learned

- Sync success is **not binary** — partial syncs happen and must be caught  
- Always check the **backend**, not just the app UI  
- BLE handoff isn’t reliable under stress — tests must simulate **bad Wi-Fi**, **low battery**, and **multi-app scenarios**  
- QA without data validation = risk to real-world users

---

## Last Updated: May 2025

