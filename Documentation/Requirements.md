
# Sensor Node Requirements List

### **1. Measurement Parameters**

- **Soil Moisture:**
    - Measurement Range: 0% to 100% volumetric water content (VWC).
    - Accuracy: ±2% VWC.
    - Measurement at a depth between 0 - 90cm.
- **Soil Temperature:**
    - Measurement Range: -20°C to +40°C.
    - Accuracy: ±0.5°C.
    - Measurement at a depth between 0 - 90cm.
- **Soil Water Tension:**
    - Measurement Range: 0 to 239 kPa.
    - Accuracy: ±5 kPa.
    - Measurement at three depths: 30 cm, 60 cm, 90 cm.

---

### **2. LoRaWAN Communication**

- **Frequency Band:** EU868 MHz.
- **Protocol:** LoRaWAN Class A.
- **Transmission Interval:** Configurable, default every 360 minutes.
- **Connection:** The Things Network (TTN).
- **Join Method:** OTAA or ABP (both possible).

---

### **3. Power Supply**

- **Battery Operated:** Yes.
- **Battery Type:** Replaceable (e.g., lithium batteries).
- **Battery Life:** At least 3 years with a transmission interval of 360 minutes.
- **Energy Efficiency:** The sensor must operate energy-efficiently to maximize battery life.

---

### **4. Enclosure and Environmental Protection**

- **Waterproof Rating:** IP68 (fully waterproof, even when permanently buried underground).
- **Material:** UV-resistant, corrosion-resistant, and robust against mechanical stress.
- **Form Factor:** Compact and suitable for installation in the root ball area (e.g., slim design for easy insertion into the soil).
- **Mounting:** Easy installation without additional tools (e.g., earth spike or similar).

---

### **5. GPS Module**

- **Location Tracking:** Integrated GPS module for accurate sensor location determination.
- **Accuracy:** ±25 meters.
- **Power Consumption:** GPS should only be activated when needed to save energy (e.g., during installation or maintenance).

---

### **6. Data Management**

- **Data Format:** JSON.
- **Data Transmission:** Via LoRaWAN to TTN.
- **Data Points:** Soil moisture, soil temperature, and soil water tension at three depths (30 cm, 60 cm, 90 cm) as well as GPS coordinates.
- **Data Integrity:** Error correction mechanisms to ensure data quality.

---

### **7. Lifespan and Maintenance**

- **Sensor Lifespan:** At least 5 years in continuous operation.
- **Maintenance-Free Operation:** The sensor should operate maintenance-free, except for battery replacement.
- **Battery Replacement:** Easy battery replacement without special tools.

---
