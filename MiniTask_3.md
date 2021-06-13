# MiniTask-3 - Debugging Tutorial


# Auto Intensity Control of Street lights

### Mechanism :
### DS1307 Real time clock -- LDR -- Microcontroller -- LCD Display of Time -- LED Array

The issue with the circuit might be due to one or more of the above components.
Does all the modules light up?
If yes go with the below ones on testing everything individually

If NO? the module which does not glow might have been mishandled and shorted or the connections might be wrong or loosely connected. If shorted we have to replace it with another one, is misconnected go through the data sheet and connect it properly and intact.

If some module is hot?
Then there is a problem with the circuit it can behave differently in sometime as something might have been burnt, if so replace it with another one and check the connections properly that might be responsible for burning the module.

**Testing RTC :** If you had a Master I2C/SMBus Engine tool built up, you could connect just it and the DS1307 together (with pull-ups and other essentials of course) and quickly see if you can communicate with the DS1307 in a few minutes. If you can, then you know that your DS1307 is working and it could be your C code
	
**Testing LDR :** LDR (light dependent resistance) can be very easily tested by using a digital multimeter. We all know that the resistance of an LDR varies according to the light falling on it. At bright light, the LDR resistance will be around 500Ohms and at darkness the resistance will be around 200K. For a proper diagnosis we need to measure the resistance of the LDR at bright light and at darkness. First in bright light connect the LDR leads to multimeter terminals the resistance is expected to be low around 500 ohms, Next cover it with an opaque paper and measure the resistance is expected to be high around 200 K ohms. If the resistance values under different conditions show the same trend then LDR is working properly.
	
**Testing Arduino :** If RTC and LDR Lights up , but you cannot upload code to Arduino and if the IC is hot , you would have probably burnt it , but shorting an Arduino isn't easy , they have inbuilt mechanisms to prevent it so check other components before concluding that the Arduino might have shorted.

**Testing LCD Display :** Add your LCD display and potentiometer to your breadboard. Connect the power and ground pins on your LCD, which are Pins 15 and 16, respectively. Connect the ground and power for your LCD’s backlight, which are Pins 1 and 2, respectively. Connect the control pins for your LCD to the digital pins on your Arduino. Now connect the potentiometer, which controls the display’s contrast. The center pin of the potentiometer should go to Pin 14 of the LCD display and the other two pins of the potentiometer are connected to power and ground, in any order. First you need to upload some code to make sure that the LCD is working properly. This code is the first part of your alarm clock sketch. You build upon it to add all the other functions for your clock. When this code is uploaded, you should see the message displayed on the LCD. If you don’t see anything, or if the display has garbled characters, you’ve connected something incorrectly. Go back to the wiring table.

**Testing LED's :** We can test the LED's using a Multimeter, the multimeter with a diode setting is needed, the red and black test leads should be connected to the outlets on the front of the multimeter. The red lead is the positive charge. The black lead is the negative and should be plugged into the input labelled COM. Connect the black probe to the cathode and the red probe to the anode, this connection should cause the LED to light up. When the probes are touching the cathode and anode, an undamaged Led light should display a voltage of approximately 1600 mV. If no reading appears on your screen during the test, start again to make sure the connections were made properly. If you have performed the test properly, this may be a sign that the LED light is not working 
	
Using the above mentioned methods we can test and Debug all the components of the circuit one by one based on the suspicions we identify and following this method recursively we can get the circuit working.
	
	
# Obstacle Avoiding Robot 

### Mechanism :
### Ultrasonic Sensor -- Microcontroller -- Motor Driver -- Servo Motor 

The issue with the circuit might be due to one or more of the above components.
Does all the modules light up?
If yes go with the below ones on testing everything individually

If NO? the module which does not glow might have been mishandled and shorted or the connections might be wrong or loosely connected. If shorted we have to replace it with another one, is misconnected go through the data sheet and connect it properly and intact.

If some module is hot?
Then there is a problem with the circuit it can behave differently in sometime as something might have been burnt, if so replace it with another one and check the connections properly that might be responsible for burning the module.

**Testing Ultrasonic sensor :** The ultrasonic sensor (eyes) on the front of your robot is used to estimate the distance to an object in front of the robot.  It does this by “pinging” (emitting an ultrasonic signal which bounces back to a sensor over the “eyes”).  The code then converts the duration of the time it took to emit and sense the signal to a distance. When the robot is plugged into your computer, and you have an open serial monitor (select “Tools” from your Arduino IDE menu), you will see a continuous stream of output in the monitor describing the distance (in CM) of an object in front of the robot’s ultrasonic sensor (eyes): 
```
// Ultrasonic sensor pins
#define echoPin A0
#define pingPin 3
void setup() {
// put your setup code here, to run once:
Serial.begin(9600);
// ultrasonic sensors
pinMode(pingPin, OUTPUT);
pinMode(echoPin, INPUT);
}
void loop() {
// put your main code here, to run repeatedly:
int distance = msToCm( ping() );
Serial.println(distance);
}
// Helper function to manage our ultrasonic sensor.
long ping() {
long duration;
digitalWrite(pingPin, LOW);
delayMicroseconds(2);
digitalWrite(pingPin, HIGH);
delayMicroseconds(10);
digitalWrite(pingPin, LOW);
duration = pulseIn(echoPin, HIGH);
return duration;
}
long msToCm(long microseconds) {
return microseconds / 29 / 2;
}
```

**Testing Motor Driver :** Try writing Code setting l1 HIGH and l2 LOW and check if the motors rotate. Because if it doesn't then the problem is usually with the Motor driver and a motor driver can be destroyed easily. So , Make sure you don't short it / Power it on before checking your circuit twice.
```
int l1 = 6;
int r1 = 5;
int l2 = 4;
int r2 = 3;
	void setup() {
  delay(500);
  Serial.begin(9600);
  pinMode(l1, OUTPUT);
  pinMode(l2, OUTPUT);
  pinMode(r1, OUTPUT);
  pinMode(r2, OUTPUT);
  digitalWrite(l1, HIGH);
  digitalWrite(r1, HIGH);
  digitalWrite(l2, LOW);
  digitalWrite(r2, LOW);
}
	void loop() {
}
```
See any movement ? Then Motor Driver is working Properly ( Make sure the Wires touch the Metal Contact in the motors)

**Testing Microcontroller :** If all other modules Lights up , but you cannot upload code to microcontroller and if the IC is hot , you would have probably burnt it , but shorting an microcontroller isn't easy , they have inbuilt mechanisms to prevent it so check other components before concluding that the microcontroller might have shorted.

**Testing Servo Motor :** Using an Ohm Meter, Disconnect ONLY 3-phase motor lines (T1,T2,T3) from the drive. Test while the cable is still connected to the servo motor first. As long as the reading is infinite, there is no issue. However, if the reading is 0 (zero) or if there is any continuity, you can be sure that a problem exists. Now disconnect the cable and test the servo and the cable separately. Make sure that the leads on both ends are not touching anything, including other leads.

Using the above mentioned methods we can test and Debug all the components of the circuit one by one based on the suspicions we identify and following this method recursively we can get the circuit working.

