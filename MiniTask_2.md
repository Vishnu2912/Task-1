# MiniTask-2
# Flow of the Project
### Auto Intensity Control of Street Lights

**Problem Statement :** Controlling the intensity of the street light based on the time and the lighting of the environment.

**Ideation and Planning : Mechanism**   
DS1307 Real time clock -- LDR -- Microcontroller -- LCD Display of Time -- Street light Intensity
### Part of the Pipeline to break : 

|Part of the Pipeline	| Feasibility	| Advantages | Disadvantages |
|---------------------|-------------|------------|---------------|
|Real time clock (DS1307)|	Based on the time the intensity of the light is to be varied.	|Accurately keeps track of seconds, minutes, hours, ability to generate Programmable Square wave. Low current use.|	Loses about 5 seconds a day as compared to NIST's time of day.|
|LDR	|Required to change the intensity of the light depending on the light in the surrounding environment.|	Using LDR and RTC produces accurate results. High sensitivity, easy employment, Low cost, High light-dark resistance ratio.|	Low temperature stability for the fastest materials, slow response in stable materials.|
|Microcontroller (ATmega8)	|Low power CMOS 8-bit microcontroller based on the AVR RISC architecture, executes powerful instructions in a single clock cycle.|	Generally contain 3 timers/counters. While two 8-bit timers can also be used as counters, the third one is a 16-bit counter. These are used to generate precision output signals, count external events or measure parameters of input digital signal.|	Long procedures to write simple code compared to that of an Arduino. |
|LED Array|	Using High Intensity LED's saves energy, most commonly found street lights are High Intensity Discharge Lamps which consume a lot of power.|	Using LED Array reduces the cost. Have longer lifetime. Low maintenance and power consumption, High efficiency.|	LED performance largely depends on the ambient temperature of the operating environment or thermal management properties.|

From the above we can choose RTC for improvements.   
* The DS-1307 is often the default choice for an RTC.  
* The DS3234 has the distinction of using an SPI interface instead of I2C.  
* The RV-1805 draws so little power that this Sparkfun module gets by without a backup battery at all.  
* The RTC Pi, a cheap and simple solution to keeping the Pi in sync when away from the Internet.  

**Prototyping phase :**  
In this phase we connect the circuit using the components and check if we get the expected results, we need to Test and Debug it until we achieve what we expected. If problem persists then we need to go to the Ideation Phase and redo the parts which breaks apart in the actual circuit.  
**Limitations of this circuit :**   
* Even though energy is saved if there are any vehicles after fixed time, intensity of the light is low.  
* Maximum energy cannot be saved.  


# Obstacle Avoiding Robot 

**Problem Statement :** Robot which avoids collision with obstacles using distance sensors.

**Ideation and Planning : Mechanism**  
Ultrasonic Sensor -- Microcontroller -- Motor Driver -- Servo Motor   
**Part of the Pipeline to break :**

|Part of the Pipeline|	Feasibility	| Advantages | Disadvantages |
|--------------------|--------------|------------|---------------|
|Ultrasonic Sensor(HC-SR04) | Minimum range 2 cm, Ranging Accuracy 3mm, for our application it is suited.|	Provides outstanding range of non-contact detection with high accuracy and stable readings.|	Sensitive to variation in Temperature, Difficulties in reading reflections from soft, curved, thin and small objects.|
|Microcontroller (Arduino)	| Feasible for prototyping but for large scale it is expensive and in the factory there is too much electrical noise and can't function well.|	Programming is very easy and can easily be modified, Doesn't require the Arduino Motor shield.| Weaker processing power and lesser working memory|
|Motor Driver (L293D)	| Two power sources needed one for Arduino, Ultrasonic Sensor, Servo Motor and the other one for L293D Motor Driver.| It can run the motor in both the directions clockwise and anticlockwise. Which is suited for our application as the robot can move in any direction.|	L293D can output maximum current of 600 mA whereas L298N can output 2 A, so L293D is used for controlling motors rated at low current.|
|Servo Motor(SG90)	| Inexpensive, made of plastic to keep it lighter and less costly. Can rotate approximately 180 degrees (90 in each direction).|	High output power, High efficiency, More constant torque at higher speed, High acceleration.|	Requires tuning to stabilize the feedback loop, unpredictable when something breaks, Peak torque is limited to 1% duty cycle.|

From the above we can choose Ultrasonic sensor, Motor driver for improvements.   
* We can use an IR Transmitter-receiver pair instead of Ultrasonic Sensor HC-SR04, Ultrasonic sensors work using sound waves, detecting obstacles is not affected by as many factors. If reliability is an important factor in your sensor selection, ultrasonic sensors are more reliable than IR sensors. If you're willing to compromise reliability for cost, infrared sensors are ideal for your application.
* L298N is a substitute for L293D the it gives a higher output current compared L293D so if the motor is not rated at low current then it can be substituted.

**Prototyping Phase :**
* In this phase we build the robot using the components and check how much of our theoretical intuition has worked, we need to Test and Debug it until we achieve what we expected. If problem persists then we need to go to the Ideation Phase and redo the parts which breaks apart in the actual circuit. 
* Obstacle avoiding robots can be used in almost all mobile robot navigation systems.
* They can be used for household work like automatic vacuum cleaning.
* They can also be used in dangerous environments, where human penetration could be fatal.
