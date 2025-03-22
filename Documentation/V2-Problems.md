
# **V2 System: Identified Issues and Problems**

While the V2 system introduces significant improvements over V1, an issue has been identified with the battery voltage measurement circuit. This document outlines the problem, its likely cause, and potential solutions.

---

## **1. Battery Voltage Measurement Circuit Inaccuracy**

### **Issue**:

The battery voltage measurement circuit in V2 reports incorrect voltages. Specifically:

- At a true battery voltage of **4.2V**, the circuit reports **3.6V**.
- At a true battery voltage of **3.3V**, the circuit reports the correct voltage.

### **Likely Cause**:

The issue is likely caused by **using the same GPIO ADC pin that the development board's internal voltage divider circuitry also uses**.

This creates a conflict in the voltage measurement, as the internal and external circuits interfere with each other, leading to inaccurate readings.

### **Impact**:

- Inaccurate battery voltage readings can lead to incorrect battery status monitoring.
- This may result in premature low-battery warnings or unexpected shutdowns, reducing system reliability.

### **Proposed Fix**:

- **Use a Dedicated ADC Pin**: Ensure the battery voltage measurement circuit uses a GPIO ADC pin that is not shared with the development board's internal circuitry.
