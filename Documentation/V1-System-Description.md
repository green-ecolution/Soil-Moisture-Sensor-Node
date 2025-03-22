
# **Summary of the Overall System**

V1 is a reference implementation for a sensor node designed to integrate with the Green-Evolution system. It is structured as a sensor rod intended for burial in the soil, housing all necessary sensor and electronic components. The system primarily consists of the V1 PCB, V1 3D-printed parts, and the following key elements:

1. **Sensors**: The Watermark 200SS (soil water tension) and SMT-100 (soil water content and temperature) measure soil conditions at depths of up to 90 cm.
2. **Electronics**: A microcontroller housed in a waterproof enclosure reads sensor data and transmits it via LoRaWAN.
3. **Power Supply**: A battery ensures reliable long-term energy supply.
4. **Data Transmission**: Wireless communication via LoRaWAN enables efficient and seamless soil moisture monitoring.

---

# **Sensors Used**

### **1. Watermark 200SS Sensors**

- **Function**: Measures soil water tension (in kPa).
- **Why Watermark 200SS?**
    - The Watermark 200SS sensors were selected based on recommendations from arboriculture professors and industry experts, including TreeSense and ARBOR revital.
    - **Proven Technology**: These sensors are widely used in both industrial and scientific applications, demonstrating reliability and accuracy.
    - **Robustness**: Suitable for various soil types and conditions.
    - **Long-Term Stability**: Delivers consistent results over many years.
- **Application**: Three Watermark sensors are attached to the rod, measuring soil water tension at depths of 30 cm, 60 cm, and 90 cm.

### **2. SMT-100 Sensor**

- **Function**: Measures soil water content (volumetric percentage) and soil temperature.
- **Why SMT-100?**
    - The sensor was chosen based on recommendations from arboriculture professors and industry experts.
    - **Scientific Accuracy**: Designed for scientific and industrial use, providing highly precise data.
    - **Multifunctionality**: Measures both water content and temperature, essential for comprehensive soil condition analysis.
    - **Reliability**: Robust and suitable for diverse environmental conditions.
- **SMT-100 Versions**:
    - The RS485 version was selected due to its availability.
- **Application**:
    - The SMT-100 is placed freely in the ground, connected only by cable to the rod. This simplifies rod production and allows flexible sensor placement, as the depth of the SMT-100 is less critical.
    - Only one SMT-100 sensor is used, as the primary focus is on the Watermark sensors. The SMT-100 complements the Watermark data by providing additional soil water content and temperature measurements, which are necessary for calibration.

### **Why This Combination?**

- **Comprehensive Soil Moisture Analysis**:
    - The Watermark sensors measure soil water tension, indicating how strongly water is bound in the soil. The SMT-100 provides volumetric water content and temperature, enabling a complete understanding of soil conditions.
- **Proven Technology**:
    - Both sensor types are well-established in industry and science, ensuring reliability and accuracy.
- **Practical Application**:
    - Combining these sensors on a single rod simplifies handling and allows precise placement at desired depths.

---

# **Other Components / Electronics**

### **Waterproof Enclosure for Electronics**

- **Positioning**: The enclosure is located at the top end of the rod, just a few centimeters below the soil surface when the rod is buried.
- **Advantages of Fully Underground Positioning**:
    - **Protection Against Vandalism**: Being underground safeguards the enclosure from damage or theft.
    - **Discreet Integration**: The electronics do not interfere with maintenance or activities around the tree (e.g., mowing, watering).
    - **Weather Protection**: The waterproof enclosure protects the electronics from moisture and other environmental factors.
- **Disadvantages**:
    - Access to the system is more challenging, particularly for battery replacement or full removal of the sensor rod.
    - LoRa reception is weaker underground.

---

### **Electronics in the Enclosure**

The electronics serve as the "brain" of the system and include the following components:

1. **Microcontroller (Heltec WIFI LoRa V3)**:
    - **Function**: Controls sensor data reading and communication with the LoRaWAN network.
    - **Why Heltec WIFI LoRa V3?**
        - Includes an integrated LoRa module.
        - Provides sufficient GPIO pins to connect all sensors.
        - Features an integrated battery management system.
2. **Sensor Interface**:
    - **Function**: Connects the sensors (Watermark 200SS and SMT-100) to the microcontroller.
    - **Watermark Sensors**:
        - A multiplexer is used to connect the Watermark sensors to the microcontroller, following the [manufacturer's example implementation](https://www.irrometer.com/200ss.html).
    - **SMT-100-RS485**:
        - A UART-TTL to RS485 module facilitates communication between the microcontroller and the sensor using ASCII commands.
3. **LoRaWAN Module (Integrated in Microcontroller)**:
    - **Function**: Transmits sensor data wirelessly via the LoRaWAN network.
    - **Advantages**: Low energy consumption, long range, and excellent penetration through obstacles (e.g., soil, vegetation).
4. **GPS Module**:
    - **Function**: Determines the sensor's position.
    - **Component**: NEO6M, chosen for its widespread availability and common use.
5. **Power Supply**:
    - **Battery**: An 18650 rechargeable cell powers the system.
    - **Energy Efficiency**: The use of LoRaWAN and an energy-efficient microcontroller ensures low power consumption, enabling extended operation with a single cell.
    - **Ruggedness**: 18650 cells are safer to handle than LiPo batteries.

---

### **Data Transmission via LoRaWAN**

- **Function**: Sensor data is transmitted wirelessly via the LoRaWAN network to The Things Network (TTN).
- **Advantages**:
    - **Low Energy Consumption**: Ideal for battery-operated devices.
    - **Long Range**: Data can be transmitted over several kilometers.
    - **Reliability**: LoRaWAN is robust and performs well even in challenging environments (e.g., rural areas or underground).
- **Why TTN?**
    - It is the most widely recognized publicly available LoRaWAN network.
    - It is used by project stakeholders, ensuring compatibility and ease of integration.
