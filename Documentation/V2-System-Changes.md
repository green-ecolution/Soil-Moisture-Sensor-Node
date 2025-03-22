
# **V2 System: Major Changes to V1**

The V2 system introduces several significant changes to address the shortcomings of V1 and improve overall performance, reliability, and usability. Below is a detailed description of the major updates implemented in V2.

---

### **Disclaimer**

This document assumes familiarity with the **V1 system description**.
 It focuses on detailing the changes and improvements made in the V2 
system. For a comprehensive understanding of the overall system 
architecture, components, and functionality, please refer to the **V1 system documentation**.

---

## **1. New Form Factor (Not Compatible with V1)**

### **Change**:

The V2 system features a completely redesigned form factor, which is not compatible with the V1 design.

### **Reason for Change**:

- The V1 form factor had limitations in terms of component placement.
- The change in components required a change in PCB design.
- The new design prioritizes better integration of components and less external connections.

### **Impact**:

- The new form factor has a increased size.
- However, it requires new enclosures, mounting hardware, and assembly processes, making it incompatible with V1 components.

---

## **2. Corrected Step-Up Converter for SMT100**

### **Change**:

The faulty step-up converter in V1 has been corrected to properly power the SMT-100 sensor in its RS-485 variant.

### **Reason for Change**:

- The V1 step-up converter did not function due to incorrect component selection and diode placement.
- This prevented the SMT-100 sensor from operating correctly.

### **Impact**:

- The corrected step-up converter ensures reliable power delivery to the SMT-100 sensor.
- This improves the accuracy and reliability of soil moisture and temperature measurements.

---

## **3. Use of an SMD GPS Module with Integrated Antenna**

### **Change**:

V2 replaces the NEO6M GPS module with a surface-mount device (SMD) GPS module that includes an integrated antenna.

It is replaced with a Quectel LC86GAAMD

### **Reason for Change**:

- The NEO6M module in V1 had poor reception, especially when buried underground.
- The NEO6M is a external module that requires additional connections and is not tightly integrated in to the PCB.
- The integrated antenna in the SMD module improves signal reception when used with a large enough ground plane underneeth the antenna which can be achieved with a custom designed PCB.
- Simplifies the design and connections.
- The Quectel LC86GAAMD was choosen for its availability at Digikey.

### **Impact**:

- Enhanced GPS performance, even in challenging environments.
- Reduced complexity and space requirements due to the integrated antenna.

---

## **4. Added Reverse Polarity Protection for the Battery**

### **Change**:

Reverse polarity protection has been added to the battery circuit to prevent damage from incorrect battery installation.

### **Reason for Change**:

- V1 lacked protection against reverse polarity, risking damage to the electronics if the battery was installed incorrectly.

### **Impact**:

- Increased robustness and user-friendliness.
- Prevents costly damage to the system due to user error.

---

## **5. Direct Power Supply to the Microcontroller via 3.3V Pin**

### **Change**:

The microcontroller is now powered directly through its 3.3V pin, with a low-dropout regulator (LDO) regulating the battery voltage. The development board's battery connection and power regulation circuitry are no longer used.

### **Reason for Change**:

- The V1 design relied on the development board's power management, which is only available through JST connector on the underside of the devboard.
- Direct power supply simplifies the design and gives greater control over component selection.

### **Impact**:

- Simplified circuitry.

---

## **6. Added Components for Battery Voltage Measurement**

### **Change**:

Additional components have been added to measure the battery voltage, which was previously unnecessary because it was handled by the development board's power management.

### **Reason for Change**:

- With the removal of the development board's power management, battery voltage measurement is now required for monitoring and low-battery alerts.

### **Impact**:

- Enables accurate monitoring of battery status.
- Ensures timely battery replacement or recharging, preventing unexpected system shutdowns.

---

## **7. Unchanged Sensors and Auxiliary Hardware**

### **Change**:

All sensors (Watermark 200SS, SMT-100) and their auxiliary hardware remain unchanged from V1.

### **Reason for No Change**:

- The sensors performed well in V1 and met the system requirements.
- No issues were identified with the sensor hardware that necessitated a redesign.

### **Impact**:

- Ensures continuity and reliability of sensor data.
- Reduces development time and cost by reusing proven components.

---

## **8. Redesigned Case Due to PCB Form Factor Change**

### **Change**:

The case has been redesigned to accommodate the new PCB form factor. However, the 3D-printed parts for the rest of the rod remain unchanged.

### **Reason for Change**:

- The new PCB form factor required adjustments to the case design for proper fit and functionality.
- The rest of the rod's design was already optimized and did not require modification.

### **Impact**:

- The redesigned case ensures compatibility with the new PCB.
- The unchanged 3D-printed parts for the rod maintain consistency and reduce manufacturing complexity.

## **9. Larger External LoRa Antenna for Improved Reception**

### **Change**:

The V2 system now uses a **larger external LoRa antenna** instead of housing it inside the enclosure. This change was made to significantly improve wireless communication performance.

### **Reason for Change**:

- In V1, the LoRa antenna was placed inside the enclosure, which severely
limited signal strength and range, especially when the device was buried underground.
- Moving the antenna outside the enclosure reduces signal attenuation caused by the enclosure material and soil interference.

---

### **Impact**:

- **Enhanced Signal Strength**: The external placement of the antenna drastically improves signal
reception, even in challenging environments like underground or areas with dense vegetation.
- **Increased Range**:
The larger antenna and its external placement allow for longer
communication distances, making the system more effective in large or
remote areas.
- **Improved Reliability**: Reduced data loss and more consistent transmission performance, ensuring reliable communication with the LoRaWAN network.

### **Design Considerations**:

- **Waterproofing**: The antenna connection point was designed to maintain the enclosure's waterproof integrity while allowing the antenna to be mounted externally.
- **Durability**: The external antenna is ruggedized to withstand environmental factors such as moisture, UV exposure, and mechanical stress.
- **Placement**: The antenna is positioned to minimize interference and maximize signal quality, ensuring optimal performance.

---

## **Summary of V2 Changes**

1. **New Form Factor**:
    - Redesigned for improved assembly, waterproofing, and component integration.
    - Not compatible with V1 components.
2. **Corrected Step-Up Converter**:
    - Ensures reliable power delivery to the SMT-100 sensor.
3. **SMD GPS Module with Integrated Antenna**:
    - Improves GPS reception and simplifies the design.
4. **Reverse Polarity Protection**:
    - Prevents damage from incorrect battery installation.
5. **Direct Power Supply to Microcontroller**:
    - Simplifies power management and improves energy efficiency.
6. **Battery Voltage Measurement**:
    - Enables accurate battery status monitoring.
7. **Unchanged Sensors and Auxiliary Hardware**:
    - Reuses proven components from V1.
8. **Redesigned Case**:
    - Accommodates the new PCB form factor while keeping the rest of the rod's 3D-printed parts unchanged.

---

## **Conclusion**

The V2 system represents a significant evolution from V1, addressing key issues and introducing improvements in design, functionality, and reliability. While the changes are substantial, they are necessary to create a more robust and user-friendly IoT sensor node. These updates lay the foundation for future iterations and ensure the system meets the demands of real-world deployment.
