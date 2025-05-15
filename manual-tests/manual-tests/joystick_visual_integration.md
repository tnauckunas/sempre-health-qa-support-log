# Joystick Visual Integration Testing – Sempre Health  
**Engineer:** Tomas Nauckunas  
**Scope:** Admin Panel Access, Joystick UI Feedback, Sensor-Triggered App Behavior  
**Period:** 2020–2022

---

## 🎯 Objective

To verify that joystick-based user input correctly triggered visual feedback within the Sempre Health iPad app interface, especially in patient exercise scenarios. Tests were run via hidden admin mode to simulate patient behavior and validate joystick responsiveness in relation to on-screen indicators.

---

## 🛠️ Admin Panel Access

- Sempre app included a hidden admin/debug mode, accessible by tapping 5 times on the left side of the screen  
- Used this to:
  - Simulate login events  
  - Monitor live joystick pairing status  
  - Trigger manual override states  
  - Access live input logs and sensor feedback in test mode

---

## 🔄 Testing Focus

1. **Joystick Auto-Pairing**
   - Verified pairing upon app open and simulated patient login  
   - Confirmed automatic detection without manual re-pairing  
   - Logged cases where pairing silently failed and fallback steps used

2. **UI Input Feedback**
   - Moved joystick in 3D space  
   - Confirmed iPad UI reflected accurate orientation + input signal  
   - Verified joystick displayed correct quadrant detection (e.g., left toe, right shoulder)

3. **3D Avatar Reaction**
   - App shows full-body patient avatar  
   - Tested whether joystick input moved the correct limb or triggered the proper exercise suggestion  
   - Logged latency when app failed to react to joystick gesture

4. **Exercise Completion Simulation**
   - Simulated exercise: “Touch left toe from upright position”  
   - Confirmed app logs:
     - Start of exercise  
     - Midpoint (motion detected)  
     - Completion signal (end position)  
   - Validated success message or alert if motion incomplete

---

## 🧪 Observed Issues

| Type | Description | Resolution |
|------|-------------|------------|
| Visual Lag | App failed to reflect joystick motion in real time | Background app restart resolved issue |
| Ghost Input | Joystick displayed movement on UI without actual input | Re-pair + reboot fixed issue |
| Avatar Misalignment | Wrong limb triggered by joystick | Issue logged and firmware report submitted |
| Incomplete Exercise Log | Movement started but didn’t complete in logs | App timeout adjusted and tested again |

---

## ✅ QA Outcomes

- Helped Sempre QA team identify and log real user interface mismatches  
- Validated accessibility hardware feedback systems  
- Documented pairing reliability and reaction time variance  
- Suggested app-side motion threshold tuning and avatar animation fixes

---

## 💡 Lessons Learned

- Input devices must be tested for *visual feedback accuracy*, not just connection  
- Debug panels = powerful tools to simulate edge-case interactions  
- Assistive tech must be tested like medical-grade devices — no signal loss tolerated  
- Sensor input → animation feedback loop is **core** to patient trust

---

## 📅 Last Updated: May 2025
