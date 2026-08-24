# 💻 Firmware & Code Logic

This folder contains the core C++ firmware that drives the active monitoring and decision-making for the Regulated Power Distribution System. 

## 🔌 Development Environment & Upload Process

The code was written, compiled, and flashed using a modern embedded toolchain rather than the standard Arduino IDE. 

* **IDE:** Visual Studio Code (VS Code)
* **Extension:** PlatformIO IDE 
* **Framework:** Arduino core for STM32
* **Hardware Programmer:** ST-Link V2
* **Upload Method:** The STM32 Blue Pill was programmed via the SWD (Serial Wire Debug) pins using the ST-Link programmer. In the `platformio.ini` file, the `upload_protocol = stlink` directive was used. Compiling and flashing was executed directly through the PlatformIO build/upload interface.

---

## 🧠 Logic Flowchart

The following flowchart represents the exact execution loop the STM32 follows every 500 milliseconds. *(Note: GitHub natively supports rendering this Mermaid chart).*

```mermaid
graph TD
    A[Power On / Boot] --> B[Set PA8 LOW <br> Default Safe State]
    B --> C[Initialize I2C & INA219]
    C --> D{Sensor Found?}
    D -- No --> E[Halt System]
    D -- Yes --> F[Read Bus Voltage & Current]
    F --> G{Is Voltage between <br> 3.5V and 4.00V?}
    G -- Yes --> H[Set PA8 HIGH <br> STATUS: SAFE]
    G -- No --> I[Set PA8 LOW <br> STATUS: FAULT]
    H --> J[Wait 500ms]
    I --> J
    J --> F
