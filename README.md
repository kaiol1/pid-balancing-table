# 🎛️ Dual-Axis PID Balancing Platform (Ball on Plate)

> A closed-loop control system built to stabilize a rolling ball on a resistive plate using independent X and Y PID controllers.

📖 **Read the full engineering analysis and hardware breakdown on https://app.notion.com/p/Project-1-PID-Balancing-Table-3ece1eadcf1c80bc9875d41e824bd080?source=copy_link.**

![Project Status](https://img.shields.io/badge/Status-Completed-success)
![Hardware](https://img.shields.io/badge/Hardware-Arduino_Uno-blue)
![Control](https://img.shields.io/badge/Control_System-PID-orange)

<div align="center">
  <!-- 💡 TIP: Upload a 5-second GIF here showing the ball balancing -->
  <img src="[LINK_TO_YOUR_GIF]" alt="Balancing Platform Demo" width="600"/>
</div>

## 📌 Overview
This project demonstrates applied control theory and embedded systems design. The primary objective is to maintain a ball perfectly centered on a movable plate despite external disturbances. 

The system reads real-time continuous coordinates from a resistive touchscreen, calculates the necessary error corrections through a PID algorithm, and actuates two independent axes (pitch and roll) to balance the ball.

## ⚙️ Hardware Architecture
* **Microcontroller:** Arduino Uno
* **Sensors:** 4-Wire Resistive Touch Screen (functioning as a high-resolution XY coordinate sensor)
* **Actuators:** 2x MG996R Servo Motors

## 💻 Real-Time Telemetry & Parameter Tuning (GUI)
To avoid the highly inefficient process of re-flashing the Arduino every time a PID constant needed adjustment, I developed a custom desktop interface to monitor and control the system on the fly.

* **Dynamic PID Tuning:** The interface communicates with the Arduino via Serial, allowing me to inject new Kp, Ki, and Kd values for both axes in real-time.
* **Data Visualization:** It plots the ball’s current X and Y coordinates against the center setpoint, providing visual feedback on the system's overshoot, settling time, and steady-state error.

## 🛠️ Tech Stack
* **Hardware:** Arduino Uno, MG996R Servos, 4-Wire Resistive Touch Screen.
* **Embedded Software:** C/C++ (PID Control Logic).
* **Interface (GUI):** HTML, CSS, JavaScript (Serial Communication).

## 🧠 Control Logic & PID Implementation
The stabilization is achieved using two independent, decoupled **PID (Proportional-Integral-Derivative)** loops for the X and Y axes. 

* **Proportional (P):** Calculates the immediate error (distance from the center). A higher value reacts faster but can cause oscillations.
* **Integral (I):** Accumulates past errors to eliminate steady-state offset.
* **Derivative (D):** Predicts future errors based on the ball's velocity, providing a damping effect.

## 🚀 How to Run
1. Clone this repository.
2. Assemble the hardware according to the schematic.
3. Calibrate the touchscreen analog readings to match the physical plate dimensions.
4. Upload `main.ino` to the Arduino Uno.
5. Launch the GUI interface and connect to the correct Serial COM port.

## 🤖 AI-Assisted Workflow & Rapid Prototyping
To accelerate the development lifecycle, I leveraged advanced LLMs as pair-programming assistants throughout this project. While the physical assembly, hardware debugging, and engineering analysis were strictly manual, AI was utilized to rapidly generate boilerplate code, structure the GUI software framework, and troubleshoot mathematical edge cases in the PID logic. This modern workflow allowed me to focus deeply on system integration and control theory rather than basic syntax.

## 📈 Future Improvements
* Upgrade to a 32-bit microcontroller (like an ESP32 or STM32) to drastically increase the control loop frequency.
* Implement a Moving Average or Low-Pass Filter in software to clean the resistive sensor data before feeding it to the PID algorithm.

---
*Designed and built by [Kaio Liuti] (https://github.com/kaiol1) - Control Systems & Automation Engineering.*
