# Regulated Power Distribution System

### 🎥 Project Demonstration
<video src="Demonstration.mp4" controls="controls" style="max-width: 100%;">
  Your browser does not support the video tag. Please download the video to view it.
</video>

---

## 💡 Project Explanation
The Regulated Power Distribution System is an intelligent, active power monitoring and fail-safe distribution channel. 

Sensitive electronic components are often vulnerable to voltage spikes and brownouts. Standard unregulated power supplies cannot adapt to dynamic loads or shut themselves down during a fault condition. This project solves that problem by introducing active voltage regulation and real-time monitoring. 

The system takes raw power, steps it down to a regulated target load range, and continuously gathers telemetry (voltage and current). Using an **STM32 Blue Pill** microcontroller and an **INA219 I2C sensor**, the system evaluates this data against strict safety thresholds. If the bus voltage exits the safe operating window, the microcontroller physically cuts the circuit in milliseconds to prevent hardware damage. 

**Motto:** *Intelligent Active Monitoring — Bridging raw hardware with precise software logic.*

---

## 🧠 The Inspiration: Software Logic in the Physical World
The core idea for this project came from a simple thought experiment: *What does an `if-else` statement look like in real life?* 

In pure software programming, an `if-else` block dictates the flow of abstract data. I wanted to take that exact concept and force it to control tangible, physical power. This system is the literal, physical embodiment of a conditional statement. The microcontroller acts as a real-world gatekeeper: 

*   **IF** (Voltage is safe) ➡️ Allow the electrical current to flow. 
*   **ELSE** ➡️ Instantly break the circuit. 

It is the direct translation of a digital software concept into an active hardware reality.

---

## ⚙️ System Workflow
The operational pipeline maps the high-voltage load path independently from the logic path. The flow of power and logic is as follows:

**12V DC Source** ➡️ **LM2596 Buck Module** *(Steps voltage down)* ➡️ **INA219 Sensor** *(Reads live telemetry)* ➡️ **STM32 Microcontroller** *(Evaluates `if-else` safety logic)* ➡️ **Pin PA8** *(Executes physical switching action)* ➡️ **Safe Output** *(LED turns ON)*

---

## 🔌 Virtual Circuit Diagram
Below is the virtual hardware layout mapping the multi-rail power distribution flow:

![Virtual Circuit Diagram](ckt%20diagrams/Vitual%20diagram.png)

---

## 🛠️ Hardware & Tech Stack
* **Microcontroller:** STM32F103C8T6 (Blue Pill)
* **Current/Voltage Sensor:** Adafruit INA219 (I2C Protocol)
* **Switching Component:** Logic-Level Solid State Switch
* **Regulators:** LM2596 DC-DC Step-Down Buck Converters
* **Firmware:** C++ (Written in VS Code using the PlatformIO environment)
* **Debugging:** ST-Link V2 Programmer & USB CDC Serial Telemetry

---

## 👨‍💻 Project Team
Developed at the **Rajshahi University of Engineering and Technology (RUET)**  
*Department of Electrical and Computer Engineering*

* **Md. Yousuf** (Roll: 2310023)
* **Topu kumar Mondol** (Roll: 2310003)
* **Anindita Sarkar** (Roll: 2310029)
