# Firmware Faults & Validation Log  
**Device:** Sempre Health Kit + Joystick Peripheral  
**Client Environment:** iPad (new issue batch)  
**Test Engineer:** Tomas Nauckunas  
**Period Covered:** 2020–2022

---

## Context

As part of ongoing support, Sempre Health received a shipment of new iPads intended for patient use. Before deployment, all devices had to be validated for:

- iPadOS firmware version  
- Bluetooth stack integrity  
- Compatibility with Sempre hardware + joystick peripheral  
- General system responsiveness after update

---

## QA Actions Taken

### Firmware Version Audit  
- Manually reviewed each iPad’s iOS version  
- Devices running iPadOS <14.0 were updated via direct OTA install  
- Logged serial numbers and matched them to update batches  
- Flagged 17 devices that froze during update process → reset via DFU mode

### Security Verification  
- Ensured devices had current security patches post-update  
- Confirmed App Store + TestFlight access was not restricted by MDM blocks  
- Installed Sempre app and validated system integrity post-install

### Joystick Integration Test  
- Connected joystick via Bluetooth  
- Ran full input validation on directional inputs + pressure triggers  
- Observed lag on 2 devices confirmed due to background update process  
- Added cooldown time after initial boot before running peripheral tests

---

## Common Firmware-Related Faults

| Issue | Devices Affected | Root Cause | Resolution |
|-------|------------------|------------|------------|
| System freeze during iOS update | 26 | Low battery during update | Full charge + DFU reset |
| Sempre app crashing post-update | 35 | App not refreshed after OS upgrade | Reinstall + relogin |
| Joystick input delay | 26 | Device background processes during startup | Added post-boot delay |
| Bluetooth disconnect mid-use | 32 | Peripheral cache corruption | Re-pair joystick + restart device |

---

## Lessons Learned

- OTA updates must be conducted **after full charge and while idle**, not while multitasking  
- Post-OS updates require **app-level testing**, not just OS checks  
- External devices (joysticks) behave inconsistently across iOS versions unless tested in sequence  
- Added a pre-deployment checklist for:
  - iOS version  
  - Sempre app install  
  - Bluetooth device pair + test  
  - App sync verification  
  - Security patch log

---

## QA Contributions

- Created internal firmware validation protocol  
- Reduced faulty device shipments by catching issues before dispatch  
- Collaborated with Sempre QA lead to revise pre-deployment SOP  
- Logged all findings into device support tracker

---

## Tester Notes

This process emphasized the importance of **black box regression testing after firmware changes**, even when core systems seemed unaffected. Peripheral integration testing was especially critical when patients relied on accessibility hardware (joysticks) for input.

---

## Last Updated: May 2025

