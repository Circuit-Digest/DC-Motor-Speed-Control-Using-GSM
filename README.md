# 📡 DC Motor Speed Control Using GSM (SMS Based)

## 🚀 Project Overview

This project demonstrates how to control the **speed and direction of a DC motor remotely using SMS commands**. 

Instead of manual switches or wired control, the motor can be operated by sending predefined text messages from a mobile phone. The system uses an **Arduino Uno**, **SIM800 GSM module**, and **L298N motor driver** to achieve reliable remote motor control without internet.

---

## 🎯 Features

✔ Remote motor control using SMS  
✔ Forward and reverse direction control  
✔ PWM-based speed control  
✔ No internet required  
✔ Low-cost automation solution  
✔ Suitable for industrial and agricultural use  

---

## 🛠️ Components Required

| S.No | Component | Quantity | Purpose |
|------|------------|----------|----------|
| 1 | Arduino Uno | 1 | Main controller |
| 2 | DC Motor | 1 | Mechanical output |
| 3 | SIM800 GSM Module | 1 | Receives SMS commands |
| 4 | L298N Motor Driver | 1 | Controls motor speed & direction |
| 5 | Level Shifter | 1 | Voltage level matching |
| 6 | External Power Supply | 1 | Powers motor & GSM |
| 7 | Breadboard | 1 | Circuit setup |
| 8 | Jumper Wires | As required | Connections |
| 9 | Arduino IDE | - | Programming |

---

## ⚙️ Working Principle

1. GSM module registers to mobile network.
2. User sends predefined SMS (FWD, REV, STOP).
3. GSM forwards message to Arduino via serial communication.
4. Arduino processes command.
5. L298N motor driver controls motor direction.
6. PWM signal adjusts motor speed.

---

## 📩 Example SMS Commands

| SMS Command | Function |
|--------------|------------|
| FWD100 | Rotate forward at speed 100 |
| REV150 | Rotate reverse at speed 150 |
| STOP | Stop motor |

Speed range: **0–255**

---

## 💻 Important Code Snippets

### Include GSM Serial Library
```cpp
#include <SoftwareSerial.h>
SoftwareSerial gsm(3, 2);
```

### Motor Pin Definitions
```cpp
#define ENA 9
#define IN1 5
#define IN2 6
```

### GSM Initialization
```cpp
gsm.println("AT");
gsm.println("AT+CMGF=1");
gsm.println("AT+CNMI=2,2,0,0,0");
```

### PWM Speed Control
```cpp
analogWrite(ENA, speedValue);
```

---

## 📡 Applications

- Remote Industrial Motor Control  
- Agricultural Irrigation Pump Control  
- Automated Gates & Barriers  
- Home Automation Systems  
- Hazardous Environment Motor Control  

---

## 🔧 Troubleshooting

### GSM Not Responding
- Check power supply (minimum 2A recommended)
- Verify SIM card activation
- Confirm correct baud rate

### SMS Not Received
- Check network signal
- Use AT+CREG? to verify registration
- Ensure SMS text mode enabled

### Motor Not Rotating
- Check motor driver connections
- Ensure external battery connected
- Verify ENA pin receives PWM signal

### Motor Speed Not Changing
- Use PWM capable pin
- Ensure speed range 0–255
- Use analogWrite(), not digitalWrite()

---

## 🔮 Future Enhancements

- Add LCD display for status
- Add feedback SMS confirmation
- Control multiple motors
- Add temperature or current monitoring
- Mobile app integration

---

## 📚 Learning Outcomes

After completing this project, you will understand:

- GSM communication using AT commands
- SMS parsing in Arduino
- PWM-based motor speed control
- L298N motor driver working
- Serial communication handling
- Remote automation systems

---

## 📌 Conclusion

This project demonstrates a practical implementation of GSM-based remote motor control. By combining Arduino, SIM800 GSM module, and L298N motor driver, the system enables long-distance motor speed and direction control without requiring internet connectivity.

It is a cost-effective and scalable solution suitable for real-world industrial and agricultural applications.

---
Author :
Vedhathiri. K
