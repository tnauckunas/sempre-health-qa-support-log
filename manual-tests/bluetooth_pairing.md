# Manual Test Case – Bluetooth Pairing Process  
**Device:** Sempre Health Monitor Kit  
**Client Environment:** iPadOS 15-20
**Test Conducted By:** Tomas Nauckunas  
**Test Period:** April 2020 – April 2022

---

## Objective  
To validate the Bluetooth pairing process between the Sempre medical device and patient-issued iPad under black box testing conditions.

---

## Tools & Setup  
- Sempre Health Monitoring Device (BLE-enabled)  
- iPad Mini / iPad Air with factory settings  
- Charging cradle for device  
- Firmware v3.4 – v4.1  
- Internal testing account  
- Standard patient app installed via TestFlight

---

## Steps Performed

1. Power on device and confirm LED status  
2. Open Bluetooth settings on iPad  
3. Search for devices – confirm device ID matches issued unit  
4. Select device – wait for pairing confirmation  
5. Launch Sempre Health App  
6. Validate automatic device detection inside app  
7. Simulate measurement  
8. Ensure data appears in user dashboard  
9. Repeat process with low battery state  
10. Repeat on iPads with iOS 14.1 and 15.3 for version testing

---

## Expected Results

- Device name correctly displays in Bluetooth list  
- Successful pairing within 10 seconds  
- Device auto-connects when app launches  
- No manual re-pairing needed unless device is reset  
- Data syncs into the app dashboard within 5 seconds of reading

---

## Common Issues Observed

| Issue | Frequency | Root Cause | Resolution |
|-------|-----------|------------|------------|
| Device fails to appear | Moderate | Low battery / firmware lag | Recharge + restart |
| Pairing timeout | Low | Bluetooth stack failure | iPad restart + app re-install |
| Device paired, but no app sync | Moderate | App permissions not granted | Reset app + re-authenticate |
| Wrong device paired (nearby unit) | Rare | Similar ID | Verified labels + scan restriction added |

---

## Notes

- Black box testing helped uncover edge cases around low battery behavior and iOS version compatibility  
- Suggested internal firmware update to handle pairing retries and provide better LED status feedback to end user  
- Test logs were submitted to internal QA tracker with replication steps and screenshots (not included here)

---

## Last Updated: May 2025

