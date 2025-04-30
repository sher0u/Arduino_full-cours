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

