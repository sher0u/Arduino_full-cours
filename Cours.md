# Arduino Full Course  

---  

## 📌 Lesson 1: Basic LED Blink Program  

### 🔧 **Description**  
This is the "Hello, World!" of Arduino. The code blinks the built-in LED (connected to **pin 13**) on and off with a **500ms (0.5-second)** delay between each state change.  

### 🛠 **Hardware Required**  
- Arduino board (Uno, Nano, Mega, etc.)  
- Built-in LED (pin 13) **OR** an external LED with a resistor (220Ω)  

### 💻 **Code**  
```cpp
/*  
 * Title: Basic LED Blink Program  
 * Description: Blinks the built-in LED on pin 13 every 500ms.  
 */  

void setup() {  
  pinMode(13, OUTPUT);  // Set pin 13 as OUTPUT  
}  

void loop() {  
  digitalWrite(13, HIGH);  // Turn LED ON  
  delay(500);             // Wait 500ms  
  digitalWrite(13, LOW);   // Turn LED OFF  
  delay(500);             // Wait 500ms  
}  
// The loop runs forever, creating a blinking effect  
```  

### 📝 **Explanation**  
| Part | Function |  
|------|----------|  
| `setup()` | Runs once; configures pin **13** as output. |  
| `loop()` | Runs forever: turns LED **ON → delay → OFF → delay → repeats**. |  
| `digitalWrite()` | Sets the pin voltage to **HIGH (5V)** or **LOW (0V)**. |  
| `delay(ms)` | Pauses the program for **milliseconds**. |  

### 🔄 **Expected Output**  
- The LED blinks **every 0.5 seconds** indefinitely.  


Here's a polished **GitHub README** version for your second Arduino lesson, focusing on **variables** and LED control:

---

## 📌 Lesson 2: Using Variables to Control an LED  

### 🔧 **Description**  
Learn how to use **variables** to make your code more flexible and reusable. This example blinks an LED connected to a customizable pin with an adjustable delay time.  

### 🛠 **Hardware Required**  
- Arduino board  
- LED (+ resistor if external) → Connected to **pin 2** (default)  

### 💻 **Code**  
```cpp
/*  
 * Title: Variable-Controlled LED Blink  
 * Description: Uses variables to define the LED pin and delay time.  
 */  

int ledNumber = 2;   // Change this to match your LED pin  
int delayTime = 500; // Adjust delay time (in milliseconds)  

void setup() {  
  pinMode(ledNumber, OUTPUT);  // Set the LED pin as OUTPUT  
}  

void loop() {  
  digitalWrite(ledNumber, HIGH);  // Turn LED ON  
  delay(delayTime);               // Customizable delay  
  digitalWrite(ledNumber, LOW);   // Turn LED OFF  
  delay(delayTime);               // Same delay again  
}  
```  

### 📝 **Key Concepts**  
| Concept | Explanation |  
|---------|-------------|  
| **Variables** | Store reusable values (`ledNumber`, `delayTime`). |  
| **Flexibility** | Change behavior by editing just **two values** at the top. |  
| **Best Practice** | Use variables for values used multiple times. |  

### 🔄 **How to Customize**  
1. Change `ledNumber` to any pin (e.g., `3`, `7`, `13`).  
2. Adjust `delayTime` (e.g., `1000` = 1 second, `100` = fast blink).  

### 🎨 **Circuit Example**  
```
Arduino Pin 2 → LED (+) → Resistor (220Ω) → GND
```  
*(Diagram for external LED; omit resistor if using built-in pin 13.)*  

---  

---  
![image](https://github.com/user-attachments/assets/f91208cf-138a-4c1d-b577-3e5b7aef2ef5)


Here's a professional **GitHub README** entry for your traffic light project (Lesson 3):

---

## 🚦 Lesson 3: Traffic Light Controller  

### 🌟 **Project Overview**  
A complete traffic light system using **3 LEDs (Red/Yellow/Green)** with configurable timing and smooth transitions.  

### 📋 **Hardware Requirements**  
| Component | Pin | Color |  
|-----------|-----|-------|  
| LED 1 | 2 | Red |  
| LED 2 | 3 | Green |  
| LED 3 | 4 | Yellow/Orange |  
| Resistors | 220Ω each | - |  

**Circuit Setup:**  
```
Arduino GND → Resistors → LEDs (Cathodes)  
Pins 2/3/4 → LEDs (Anodes)  
```

### 💻 **Smart Traffic Light Code**  
```cpp
/*  
 * Title: Traffic Light Controller  
 * Features:  
 * - Realistic light sequence (Red → Green → Yellow)  
 * - Configurable timings for each phase  
 * - Smooth transitions between states  
 */

// LED Pins
const int redPin = 2;     // Red light pin
const int greenPin = 3;   // Green light pin
const int orangePin = 4;  // Yellow light pin

// Timing Settings (milliseconds)
const unsigned long redTime = 5000;      // 5s red
const unsigned long greenTime = 5000;    // 5s green  
const unsigned long orangeTime = 2000;   // 2s yellow
const unsigned short transitionDelay = 500; // 0.5s between lights

void setup() {
  // Initialize all light pins
  pinMode(redPin, OUTPUT);
  pinMode(greenPin, OUTPUT); 
  pinMode(orangePin, OUTPUT);
  
  // Start with all lights OFF
  digitalWrite(redPin, LOW);
  digitalWrite(greenPin, LOW);
  digitalWrite(orangePin, LOW);
}

void loop() {
  // Phase 1: Red Light
  digitalWrite(redPin, HIGH);
  delay(redTime);
  digitalWrite(redPin, LOW);
  delay(transitionDelay);

  // Phase 2: Green Light  
  digitalWrite(greenPin, HIGH);
  delay(greenTime);
  digitalWrite(greenPin, LOW); 
  delay(transitionDelay);

  // Phase 3: Yellow Light
  digitalWrite(orangePin, HIGH);
  delay(orangeTime);
  digitalWrite(orangePin, LOW);
  delay(transitionDelay);
}
```

### 🛠 **Key Features**  
✔ **Professional Structure** (Constants for easy customization)  
✔ **Realistic Behavior** (Includes transition delays)  
✔ **Best Practices** (All pins LOW at startup)  

### 🎓 **Learning Objectives**  
1. **Multi-LED Control**  
2. **Time Management** with `delay()`  
3. **Code Organization** using constants  

---

### 🔧 **Customization Guide**  
| Variable | Purpose | Recommended Range |  
|----------|---------|-------------------|  
| `redTime` | Red light duration | 3000-10000ms |  
| `greenTime` | Green light duration | 3000-10000ms |  
| `orangeTime` | Warning duration | 1000-3000ms |  
| `transitionDelay` | Blackout between lights | 200-1000ms |  

**Pro Tip:** Try adding a **pedestrian button** interrupt as a challenge!  

---

### 📸 **Example Output**  
```
[RED] 5s → [OFF 0.5s] → [GREEN] 5s → [OFF 0.5s] → [YELLOW] 2s → (repeats)
```
![image](https://github.com/user-attachments/assets/64918d78-6404-4fdf-8d50-98943b7fe3fb)

