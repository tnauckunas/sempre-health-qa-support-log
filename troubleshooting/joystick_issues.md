# Joystick Troubleshooting Log – Sempre Health  
**Engineer:** Tomas Nauckunas  
**Role:** QA / Field Technician  
**Scope:** Bluetooth-connected joystick → iPad UI interaction failure points  
**Period:** 2020–2022

---

## Problem Overview

A subset of Bluetooth-connected joysticks used in Sempre Health exercise kits failed to behave reliably across different test environments and iPad models. Issues ranged from unresponsive inputs to inaccurate spatial readings on the app's 3D patient interface.

Failures were most commonly observed during integration testing in debug/admin mode, where direct feedback from joystick movement was expected in real time on the iPad display.

---

## Common Issues Logged

| Category            | Description | Occurrence | Resolution |
|---------------------|-------------|------------|------------|
| **Spatial Misread** | Joystick motion showed incorrect limb movement on 3D avatar | High | Firmware checked; replacement required |
| **Node Unresponsiveness** | Tapping expected zone did nothing (e.g., no reaction when joystick contacted virtual node) | Moderate | Device reset or replacement triggered |
| **App Drift** | Joystick movement kept triggering wrong side of the avatar | Moderate | Calibrated joystick angle + tested across iPads |
| **No Input** | Joystick powered on, paired, but app didn’t react | Moderate | Device charged + firmware rechecked |
| **Inconsistent Motion Logging** | Avatar showed start of motion but didn’t log task completion | Low | QA flagged incomplete exercise flow |

---

## Testing Model Variations

We tested across multiple joystick hardware versions and iPads:

| Joystick Model | Behavior | Notes |
|----------------|----------|-------|
| Model J-14      | Most stable | Used as baseline |
| Model J-15-B    | Intermittent misalignment | Replaced in 40% of tests |
| Model J-16 (Red LED) | Poor response on touch | Fully replaced after firmware checks |

iPads tested on:
- iPad Mini (iOS 13.4)  
- iPad Gen 6 (iOS 14.8)  
- iPad Gen 7 (iOS 15.3)  

---

## Pattern Observations

- Devices with low charge (~25% battery) were more likely to drift or disconnect  
- Some joysticks only responded correctly after 10+ seconds post pairing  
- Admin mode helped isolate failure points, especially in unresponsive node targeting  
- Half of all failures could not be corrected via firmware and required hardware replacement

---

## Resolution Path

- Created hardware replacement threshold: 3+ integration failures = swap  
- Logged affected model batch IDs for vendor escalation  
- Created flow: Charge → Reset → Admin mode validation → Replace  
- Added delay buffer to allow full firmware sync before testing inputs

---

## Lessons Learned

- Hardware QA can’t be limited to “does it connect” it must include **real-time sensor accuracy**  
- Assistive devices need **visual + tactile verification**  
- Calibration across models must be standardized drift = data error = patient risk  
- Admin/debug mode testing reveals interaction issues not visible in user view

---

## Last Updated: May 2025
