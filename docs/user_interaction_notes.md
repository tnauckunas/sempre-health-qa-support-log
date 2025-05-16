# User Interaction Notes – Sempre Health Support  
**Author:** Tomas Nauckunas  
**Time Period:** 2020–2022  
**Role:** QA / Support Technician (Bluetooth Medical Devices + iPads)

---

## Purpose

To capture real-world user interactions, misunderstandings, and recurring pain points when setting up or supporting Sempre Health kits for patients. These notes helped refine onboarding steps, simplify instructions, and improve QA focus on real usage patterns.

---

## Observed User Behavior Patterns

### 1. **Confusion Around Bluetooth Pairing**
- Patients expected device to “just work” without going into Settings  
- Many attempted to pair through the app before activating Bluetooth  
- Recommendation: Add explicit popup instructions in-app during first launch

### 2. **Low Patience With Initial Setup**
- Setup taking more than 2 minutes = high frustration  
- Users often restarted the app multiple times rather than waiting for sync  
- Recommendation: Add progress spinner or pairing status indicator

### 3. **Mismatched Device IDs**
- Family homes had multiple devices nearby → wrong unit paired  
- Led to incorrect data or total sync failure  
- Recommendation: Display device ID clearly on physical label and in-app prompt

### 4. **Inconsistent Charging Behavior**
- Users thought device was faulty if no lights showed instantly when plugged in  
- Many unplugged before initial charge kicked in  
- Recommendation: Add delay-tolerant LED flash or “Charging...” text screen

### 5. **Overlooked Permissions**
- iOS prompts for Bluetooth or Local Network often skipped  
- Users didn't realize denying access caused failure  
- Recommendation: QA flagged this → updated onboarding to walk users through “Allow” flow

---

## Technician Lessons Learned

- **Don't assume the user reads the manual.** Test flows must be intuitive without documentation  
- **Every second counts.** Speed of feedback in UI is as critical as technical accuracy  
- **More transparency = fewer support calls.** Users trust systems that talk to them  
- **Human error must be tested like system failure.** “Fail to allow permissions” = test case, not edge case

---

## QA Process Enhancements Triggered

- Created new black box test cases for user denial of permissions  
- Added retry logic to sync flow when initial pairing fails  
- Suggested onboarding flow change based on 7 recurring cases  
- Developed printable 1-sheet for field reps to carry during house visits

---

## Quote from User

> “I thought it was broken. Turns out I just didn’t press ‘Allow’ when it asked. I had no idea that mattered.”

---

## Last Updated: May 2025

