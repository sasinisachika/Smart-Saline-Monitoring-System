# Smart Saline Monitoring System

## 📝 Overview
The **Smart Saline Monitoring System** is designed to enhance patient safety during IV fluid administration by detecting empty saline bottles, air bubbles, IV line disconnections, and abnormal flow rates.

Using **LabVIEW** with a **DAQ interface**, the system performs real-time data acquisition, signal conditioning, and integrates sensors with actuators to automatically respond to critical conditions—closing the IV clamp when the bottle is empty and triggering alarms for air bubbles, disconnections, or abnormal flow rates caused by issues like a bent IV line. 

---

## ⚙️ Features
- Detect empty saline bottles to prevent backflow using a **load cell** that measures bottle weight.  
- Detect air bubbles in the IV line using an **IR LED and photodiode** sensor pair.  
- Ensure proper IV line connection using a **Hall effect sensor**.  
- Detect abnormal flow rates due to line bends or blockages and trigger alarms.  
- Automated IV clamp control when the bottle is empty.  
- Real-time sensor-actuator integration and alerts via LabVIEW.  
- Real-time calculation and display of IV flow rate based on weight difference over time.  
- Calibration and visualization of measurements on LabVIEW dashboard.

---

## 🛠️ Hardware Components

 ✔ Sensors:  
- Load cell – Detects empty saline bottle (monitors volume primarily for empty condition)  
- IR LED + photodiode – Detects air bubbles in IV line  
- Hall effect sensor – Ensures proper IV line connection  

 ✔ Actuators:
- Servo motor – Automatically closes IV clamp when the bottle is empty  
- Audible/visual alarms – Alert staff for critical events  

 ✔ Other Components: 
- DAQ interface – Connects all sensors and actuators; main platform for data acquisition, signal conditioning, and control  
- Arduino Uno – Acquires some sensor readings  
- IV setup: bottle, tubing, clamp  
- Connecting wires, power supply  

---

## 💻 Software Components
- **LabVIEW** – Main platform for real-time monitoring, signal conditioning, sensor-actuator integration, calibration, visualization, and alarm management. Sensor outputs are connected to actuators in LabVIEW for automatic responses.  
- **Arduino IDE** – Used only to acquire readings from selected sensors and pass them to LabVIEW.

---

## LabView Control
LabVIEW collects and processes sensor data through the DAQ, controls actuators like the servo clamp, calculates flow rate, and displays a real-time dashboard for monitoring system status and alerts.

<img width="600" height="450" alt="Screenshot 2025-09-21 140541" src="https://github.com/user-attachments/assets/37e23e2e-449e-4188-953c-e3ecdd567942" />



<img width="450" height="500" alt="Screenshot 2025-09-21 140606" src="https://github.com/user-attachments/assets/6b0226e1-d7a8-4949-a4fb-b7d81d29e5e1" />



---

## ⚡ How the System Works
Sensors continuously monitor the IV setup:  
- **Load Cell:** Measures saline bottle level to detect when it is empty.  
- **IR LED & Photodiode (Optical Sensor):** Detects air bubbles in the IV line.  
- **Hall Effect Sensor:** Checks proper connection of the IV bottle.  

✔ Data from all sensors is processed in **LabVIEW**, which:  
- Evaluates safety thresholds for each monitored parameter.  
- Activates **audible and visual alerts** if unsafe conditions are detected.  
- Triggers the **servo-controlled clamp** automatically to prevent reverse blood flow when the bottle is empty.  
- Calculates and displays the IV flow rate in real-time by dividing weight differences over time.  
- Triggers alarms if an abnormal flow rate is detected, which can occur due to bent or blocked IV lines.  
- Provides a real-time interface for medical staff to monitor the IV setup.  
- Supports modular expansion to monitor multiple patients simultaneously.  

---

## 📝 Step-by-Step Setup
✔ **Hardware:** Connect sensors and actuators to the DAQ; Arduino handles specific sensor readings. Ensure proper power connections.  
✔ **Arduino:** Upload code and verify readings; transfer data to LabVIEW via DAQ.  
✔ **LabVIEW:** Open VI files, configure DAQ, link sensors to actuators, calibrate, and verify functionality.  
✔ **Operation:** Monitor IV setup in real-time; automatic clamp control and alarms respond to unsafe conditions. Flow rate is calculated and displayed, with alarms for abnormal rates.

---

## 🚀 Future Work
- Expand the system to monitor multiple IV setups simultaneously for larger hospital wards.  
- Integrate wireless communication for remote monitoring and alerts.  
- Incorporate additional sensors to monitor medication type, flow consistency, or temperature.  
