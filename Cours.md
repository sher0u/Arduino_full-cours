# Arduino_full-cours
-----------------------------------------------------------------------------------------------------------------------------------------------------------------------
1-the fiirst lesson in arduino :
 * Title: Basic LED Blink Program  
 * Description: This code blinks the built-in LED (pin 13) on and off  
 *              with a 500ms (0.5-second) delay between each state change.  
 * Hardware: Arduino board with an LED connected to pin 13 (or using the built-in LED).  

void setup() {  
  // Initialize digital pin 13 as an OUTPUT  
  pinMode(13, OUTPUT);  // Pin 13 is commonly the built-in LED on many Arduino boards  
}  

void loop() {  
  // Turn the LED on (HIGH voltage level)  
  digitalWrite(13, HIGH);  
  delay(500);  // Wait for 500 milliseconds (0.5 seconds)  

  // Turn the LED off (LOW voltage level)  
  digitalWrite(13, LOW);  
  delay(500);  // Wait for another 500 milliseconds before repeating  
}  

// The loop() function runs indefinitely, creating a continuous blinking effect  
-----------------------------------------------------------------------------------------------------------------------------------------------------------------------
