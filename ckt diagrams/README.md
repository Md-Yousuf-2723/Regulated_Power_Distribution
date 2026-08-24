# 📐 Circuit Diagrams & Design Process

This folder contains all the visual documentation, schematics, and raw design files used to map out the Regulated Power Distribution System before moving to physical implementation in the lab.

## 🎨 Designing in Figma

Instead of using traditional schematic software (like Proteus, Fritzing, or KiCad), the visual hardware layout for this project was designed from scratch using **Figma**. This approach provided a clean, highly readable, and presentation-ready representation of the physical breadboard layout.

### The Design Workflow
1. **Asset Collection:** High-quality images of the physical components (STM32 Blue Pill, LM2596 Buck Converters, INA219 sensor, etc.) were collected and organized. These raw visual assets are stored in the `Pic used in Figma` folder.
2. **Component Placement:** The assets were imported into the digital canvas and arranged to mimic the physical constraints and layout of an actual lab workbench.
3. **Visual Routing:** The wiring was manually mapped out using Figma's vector pen tools. The routing deliberately color-codes and isolates the 12V high-power tracks from the 3.3V/5V logic tracks, ensuring the design was electrically sound and fail-safe before a single real wire was cut.

---

## 📂 Folder Contents

* **`figma diagram.fig`**  
  The raw, editable Figma project file. You can import this directly into your own Figma workspace to view the vector layers, modify the wiring, or add new components.

* **`main ckt digram.png`**  
  A clean, block-level structural schematic showing the logical flow of power and data without the clutter of physical wires.

* **`Vitual diagram.png`**  
  The final, fully wired visual prototype showing exactly how the physical components connect to each other in reality.

* **`Pic used in Figma/`**  
  A sub-directory containing all the individual, isolated component image files used to build the virtual diagram.
