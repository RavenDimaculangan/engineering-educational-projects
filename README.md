# Multi-Node Embedded Systems, Industrial Instrumentation & Mechatronic Prototypes

## Project Overview
This repository serves as an engineering portfolio archive for the physical hardware prototypes and instrumentation systems I designed, programmed, and fabricated from my 2nd to 4th year of undergraduate studies. 

These projects span three core disciplines within automation engineering: **Distributed Internet of Things (IoT), High-Precision Signal Conditioning, and Autonomous Mechatronic Sorting Systems.**


## Core Engineering Project Catalogue

### 1. HelmoTech | Smart Helmet & Connected Fleet Telemetry Ecosystem
* **System Overview:** A multi-node IIoT safety ecosystem designed to enforce Personal Protective Equipment (PPE) compliance and automate emergency crisis response networks.
* **The Engineering Framework:** Uses internal infrared sensors to verify operator compliance. Removing the helmet triggers an asynchronous 15-second firmware countdown; if compliance is not restored, a shutdown packet is broadcast via a 433 MHz RF link to a vehicle-side receiver node, de-energizing an electromechanical ignition relay. 
* **Incident Response Pipeline:** For crash detection, an MPU6050 IMU monitors high-G impact profiles and angular orientation vectors. Upon threshold breach, the ESP32 parses live NMEA strings from a Neo-6M GPS transceiver and commands an AT-driven SIM800L GSM cellular module to broadcast automated distress coordinates.

### 2. Micro-Strain Tire Pressure Measurement System
* **System Overview:** A high-precision structural health and pressure monitoring array that translates microscopic mechanical tire strain into linear, readable voltage datasets.
* **The Engineering Framework:** Deployed a single active strain gauge configured in a quarter-bridge Wheatstone topology. To isolate the microvolt-level sensor delta from ambient electromagnetic noise and common-mode vibrations, an AD620 Instrumentation Amplifier was integrated. 
* **Calibration Loop:** Computed mathematical transfer functions to establish a specific target gain resistance ($R_G \approx 198.4\ \Omega$) to yield a stable 250x amplification factor without clipping. Utilized a dual-potentiometer calibration array, adjusting the offset trimmer to nullify inherent bridge resistance unbalance (0V baseline) and tuning the gain trimmer to optimize voltage swings to match the ADC's maximum input resolution.

### 3. Proximity-Adaptive Material Handling & Sensor-Fusion Sorting System
* **System Overview:** An industrial conveyor prototype engineered to dynamically modulate belt velocities based on target proximity while systematically identifying and classifying materials.
* **The Engineering Framework:** Fabricated the mechanical structural chassis and integrated proximity sensors to execute adaptive velocity control algorithms. At the sorting junction, an advanced sensor-fusion array was implemented: inductive proximity sensors isolated metallic targets, while capacitive/optical sensors classified non-metallic mediums. 
* **Execution & Debugging:** Programmed synchronous control loops to drive servo-actuated sorting gates, routing materials into dedicated storage bays while systematically debugging sensor false-positives and reducing hardware-software latency gaps to prevent mechanical jams.

### 4. Discrete Analog Multi-Stage Thermal Management Array
* **System Overview:** A hardwired, microcontroller-free closed-loop cooling system that dynamically scales fan velocities and triggers emergency acoustic/visual alarms via discrete hardware thresholds.
* **The Engineering Framework:** Modeled an NTC thermistor into a precision voltage divider to map temperature variations into voltage swings. Configured an array of Operational Amplifiers (LM358/LM324) as cascading voltage comparators. As the voltage crossed pre-calculated resistor reference windows, the Op-Amps sequentially engaged a network of bipolar junction transistors (BJTs), Diodes/Zener Diode to step up the fan current. A final comparator tier was configured to latch an alarm buzzer if a critical safety ceiling was breached.
* **Prototyping Pipeline:** Validated circuit loops within Tinkercad Circuits, built a breadboard proof-of-concept for thermal validation, and executed precision hand-soldering to transfer the design to a permanent printed circuit board (PCB).
