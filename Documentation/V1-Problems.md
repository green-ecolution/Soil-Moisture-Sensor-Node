
# **V1 PCB Design Issues and Fixes**

This document outlines the identified issues in the V1 PCB design, their implications, and proposed solutions for future revisions.

---

## **1. Step-Up Converter Malfunction**

### **Issue**:

The step-up converter on the V1 PCB does not function as intended. This component is critical for powering the SMT-100 sensor in its RS-485 variant.

### **Root Causes**:

- Incorrect component variants were selected during the design phase.
- The diode was placed incorrectly in the circuit (this has been corrected in the V1 schematic).

### **Temporary Fix**:

An external step-up converter can be connected to bypass the faulty PCB section, allowing the system to function until a revised PCB is available.

### **Permanent Fix for V2**:

- Ensure the correct component variants are selected.
- Verify the diode placement and circuit design to match the corrected schematic.

---

## **2. Watermark Sensors Powered with 5V Instead of 3.3V**

### **Issue**:

The Watermark sensors are being driven with 5V instead of the required 3.3V. When the soil is dry, the internal resistance of the sensors increases, causing the voltage on the ESP32 pin to rise up to 3.8V, which is outside the safe operating range.

### **Implications**:

- Risk of damaging the ESP32 microcontroller due to overvoltage.
- Inaccurate sensor readings under dry soil conditions.

### **Fix for V2**:

- Adjust the circuit to ensure the Watermark sensors are powered with 3.3V instead of 5V.
- Implement voltage regulation or protection mechanisms to prevent overvoltage on the ESP32 pins.

---

## **3. Insufficient Via Sizes for Microcontroller Pin Headers**

### **Issue**:

The via holes for the microcontroller pin headers are too small, making it difficult to assemble and solder the components properly.

### **Implications**:

- Increased risk of poor electrical connections.
- Assembly challenges, potentially leading to manufacturing delays or defects.

### **Fix for V2**:

- Redesign the PCB layout to include larger via holes for the microcontroller pin headers.
- Ensure the via sizes meet standard manufacturing and assembly requirements.

---

## **4. Poor GPS Reception**

### **Issue**:

The GPS module exhibits poor reception, which may be caused by either an inadequate GPS module or an insufficient antenna design.

### **Implications**:

- Inaccurate or unreliable location data.
- Potential failure to meet system requirements for precise positioning.

### **Fix for V2**:

- Evaluate and upgrade the GPS module to a more reliable and sensitive model.
- Optimize the antenna design and placement to improve signal reception.
- Consider adding a dedicated GPS antenna with better performance characteristics.

---

## **5. Poor LoRa Antenna Reception**

### **Issue**:

The LoRa antenna demonstrates poor reception, leading to weak or unreliable data transmission.

### **Implications**:

- Reduced communication range and reliability.
- Potential data loss or incomplete transmission.

### **Fix for V2**:

- Upgrade the LoRa antenna to a higher-quality, more efficient model.
- Optimize the antenna placement and design to maximize signal strength.
- Ensure proper impedance matching and minimal interference from other components.

---

## **Summary of Fixes for V2 PCB**

1. **Step-Up Converter**:
    - Correct component selection and diode placement.
    - Verify functionality before production.
2. **Watermark Sensor Power Supply**:
    - Ensure 3.3V operation.
    - Add voltage protection mechanisms.
3. **Microcontroller Pin Header Vias**:
    - Increase via sizes to facilitate easier assembly.
4. **GPS Reception**:
    - Upgrade the GPS module and antenna for better performance.
    - Optimize antenna placement and design.
5. **LoRa Antenna Reception**:
    - Upgrade the LoRa antenna and optimize its placement.
    - Ensure proper impedance matching and minimal interference.

By addressing these issues in the V2 PCB design, we can improve reliability, simplify assembly, and ensure the system operates within safe electrical and communication parameters.
