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
