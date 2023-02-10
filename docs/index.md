About me

I am Payal Debipersad. I'm nineteen years old. I am a mechanical engineering student at ADEK. I wanted to learn more skills, because we don't do that a lot. We are focussed on the theory. That is why I want to do this course.\
![](https://lh5.googleusercontent.com/nAiAiFeb9TBiQf5_lDf6pJBL2K9SIIBd45yWLw_ccW_uZ0iehQW9pA75a0nqkyaK9cv7iMjjmoo2h_AJyHVWbMtNI-5kQlFnVURargdeUtz3RZ1nGjQYuue24jWqT6xPWski7Tn5hBg-ASBLRaHS9g)

Day 1 (5 sept):
===============

objective :  Introduction to simple-, serie- and parallel circuits. 

Introduction to a breadboard. 

Introduction to an arduino and a push button. 

Introduction to coding and building a blinking LED.

Component list:  LED

Resistor 

Power source 

Multimeter

Diode

Breadboard

Arduino 

Push button

HandsOn:

First we made 3 circuits, simple-, serie- and parallel. We controlled the current with a resistor so that the LED wouldn't burn. After that we learned how to work with a multimeter. Then we used a breadboard and measured the resistance after adding resistors in serie and in parallel. Below you can see a screenshot of the components. 

![](https://lh3.googleusercontent.com/b4wfTUhotlZQZnOz-YEh-3eZ6bmscKIJ0RwdV9Ylr515NxnIE89yoNnQqrCCAQ5k44KP2VIpM2iKgMKOGAsgWwzzqh_Cwn-z1EC2-OO2V5G0Wsy8MY4Jsimh1EdhxlT2XAV4qG0fcUCXB5a2l7W9Sg)

After that we used an arduino to make a LED blink by the instructions that are written in a code. In a screenshot below, you can see how it is built.

![](https://lh6.googleusercontent.com/NS9W_b-yb_cF7eC2wPv1nepT3ezJ4_LCMYqWoO4XXCGapdp457ETu-DAXDMmHMhy4ik-AF0YNAiSOac1k56CQ5U-SAIaolzfIk8i49Fll0m5qoWCPQfBTXh9f5_6e6rryuECxxRerASo2oPEK4joVg)

Code:

In this code we are going to make the LED blink one second. If we are going to push the button it won't blink anymore. It will stay on.

int led = 2;

int button = 3;

void setup (){

  pinMode(led, OUTPUT);

  pinMode (button, INPUT);

}

void loop (){

  if (digitalRead(button) == LOW) {

  digitalWrite(led, HIGH);// other option: (2,1)

  delay(500);// in milliseconds

  digitalWrite(led, LOW);

  delay(500);

  } else 

  digitalWrite(led, HIGH);// other option: (2,1)

}

Mistakes:

My first mistake was that I didn't put the wire on the right place in the breadboard sometimes. My second mistake was that I didn't hold the push button in, and I thought that my code was wrong. Some other mistakes were that I would make little writing mistakes in the code and I would get an error.

Day 2 (6 sept):
===============

objective :  Usage of analog input.

Introduction to a potentiometer.

Coding a LED with a potentiometer and temperature sensor.

Component list:  LED

Potentiometer

Temperature sensor

Breadboard

Arduino 

HandsOn:

First we made a circuit with a potentiometer in it and we wrote a code to read the value of the potentiometer.

![](https://lh6.googleusercontent.com/nxO8ngjsxeaE-qmM3Xhx-VxwyAOQ5PJe2KuEpFwY8PKGnwZn03noYTL-BQhz2Nof2Eu4E1ofQ4Ucrq_-zVBgPROvtqnprHkqGPEVukqRCubqls-BG-ZtdW_y3sfO6hoP8BdWcvf46ElIU6EJ-rx6f44)

After that we put an LED in the circuit and made it light. Then we replaced the potentiometer with a temperature sensor.

![](https://lh6.googleusercontent.com/5ImZcjmUPi-r-r5tB0KViwIi1xyjy-h2T-2G1ak_By2P_2fu4XPMDmAnhCLtV-e9t0pD-36_Fggl_CJt6726wUVAamr4YnfXik2u_tMqd57P24-pz1uLSNrsruRLxYISAoYBENIc2KBWuawxDLv3RSQ)

After that we put another LED in the circuit. The LED's turn on and off in turns while we change the value of the temperature sensor. 

![](https://lh6.googleusercontent.com/hKRzbDHhyt76BkwaqywEOEeGGOxNqkFvcoXdQHh7Y_eQ-80eAWstbDi5Kf2iwFFG-IPiaGo5DxiokTWLgDFN-avexAGEzGX-e31Mz91LKspsX7ikJMMsjgWk5n2AWRxjW7YcnYuQC87Wwq8UdChzrPA)

Code:

The code for reading the value of the potentiometer:

int pot = 0;

void setup()

{

  Serial.begin(9600);

}

void loop()

{

  int pot_value = analogRead(pot);

  Serial.println(pot_value);

}

The code for reading the value of the potentiometer and turning on a LED:

int pot = 0;

int LED = 3;

void setup()

{

  Serial.begin(9600);

  pinMode(LED,OUTPUT);

}

void loop()

{

  int pot_value = analogRead(pot);

  Serial.println(pot_value);

  int LED_value = map(pot_value, 0, 1023, 0, 255);

  digitalWrite(LED,LED_value);

}

The code for reading the value of the temperature sensor and lighting up the LED's:

int temp = A0;

int LED = 3;

int LED1 = 4;

void setup(){

  Serial.begin(9600);

  pinMode(LED,OUTPUT);

  pinMode(LED1,OUTPUT);

}

void loop(){

  int temp_value = analogRead(temp);

  Serial.println(temp_value);

  int LED_value = map(temp_value, 20, 358, 0, 255);

  digitalWrite (LED, LED_value);

  if(temp_value > 250){

    digitalWrite (LED, LOW);

    digitalWrite (LED1, HIGH);

  }

  else{

    digitalWrite (LED, HIGH);

    digitalWrite (LED1, LOW);

  }

}

Mistakes:

Some of the mistakes that I made were coding errors and that I built everything in one. I didn't save the earlier work.

Day 3 (7 sept):
===============

objective :  Introduction to a servo motor and how to control it with a potentiometer. 

Introduction to a DC motor. 

Component list:  Servo motor

Potentiometer 

Arduino

Breadboard 

DC motor

L293D

HandsOn:

First we built a servo motor and coded it to turn 0, 90 and 180 degrees and we could also see the change on the display. 

![](https://lh3.googleusercontent.com/tQvZvYbi-R4wX9Nex3moXucet6VM0s_fytk4kYCs_o34E_g31B2-wx8ZIfMs7iaUcN85wuvZUBh-_mfrFnW5VJZ6lHHAGH88DcOcKWwNvSJkSL7mpG16mXFAN3APxLL6VWNy5UMpQzz2fcHA8UjtYgA)

After that we tried to control the servo motor with a potentiometer.

![](https://lh4.googleusercontent.com/ewPz2JaCwb2e3Brtvpd3VIk_K2AR0QJDsB7QOxUx0CW-wqkotp60goYPpjIGUNtnlCqxQ42rhI0DBVzHbGPlG53n-y8MhJkWDnsgumXmRVW7-T_g-004KHiNcJn1f_2F9r2vxMMgI48yMjbkcB3pFBU)

After this we learned about a DC motor and how to control it with a L293D. And the challenge was to work with 2 DC motors. 

![](https://lh5.googleusercontent.com/vZJV0lDBWYSngXa-9Xyp-jkosS2PyfxmRV3hDicfG9Z-lXKR_J2xM5KQ3_0j1MMyWMnwkuteglacpJ90mBK3EvwVJ58kO_J762b-e8ght_h5x6dP3OO317-J96zcVTp4eSxS-a8dXP1dSPpEoPrQi_g)

Code:

For the servometer:

#include <Servo.h>

Servo myservo;

int servoPin = 3;

void setup()

{

  myservo.attach(servoPin);

  Serial.begin(9600);

}

void loop()

{

  myservo.write(0);

  Serial.println("0 degrees");

  delay(2000);

  myservo.write(90);

  Serial.println("90 degrees");

  delay(2000);

  myservo.write(180);

  Serial.println("180 degrees");

  delay(2000);

}

For the servo motor with the potentiometer:

#include <Servo.h>

Servo myservo;

int servoPin = 3;

int pot = A0;

int pot_value;

int servo_value;

void setup()

{

  myservo.attach(servoPin);

  Serial.begin(9600);

}

void loop()

{

  pot_value = analogRead(pot);

  servo_value = map(pot_value, 0, 1023, 0, 180);

  myservo.write(servo_value);

  Serial.println(servo_value);

}

For the DC motors:

int motor1enable = 3;

int motor1input1 = 2;

int motor1input2 = 4;

int motor2enable = 6;

int motor2input1 = 7;

int motor2input2 = 1;

void motorforward()

{

  analogWrite(motor1enable, 255);

  digitalWrite(motor1input1, LOW);

  digitalWrite(motor1input2, HIGH);

  analogWrite(motor2enable, 255);

  digitalWrite(motor2input1, LOW);

  digitalWrite(motor2input2, HIGH);

}

void motorbackward()

{

  analogWrite(motor1enable, 255);

  digitalWrite(motor1input1, HIGH);

  digitalWrite(motor1input2, LOW);

  analogWrite(motor2enable, 255);

  digitalWrite(motor2input1, HIGH);

  digitalWrite(motor2input2, LOW);

}

void setup()

{

  Serial.begin(9600);

  pinMode(motor1enable, OUTPUT);

  pinMode(motor1input1, OUTPUT);

  pinMode(motor1input2, OUTPUT);

  pinMode(motor2enable, OUTPUT);

  pinMode(motor2input1, OUTPUT);

  pinMode(motor2input2, OUTPUT);

}

void loop()

{

  motorforward();

  delay(2000);

  motorbackward();

  delay(2000);

}

Mistakes:

Again I made coding mistakes. My code would get errors. And I also made a mistake with the L293D. I forgot the order of the inputs, so that went wrong.

Day 4 (12 sept):
================

objective : Learning how to make 3D designs with thinkercad.

HandsOn:

First we learned the basics of 3D modelling. We built a house and a block with our name on it.

![](https://lh3.googleusercontent.com/DKhB6hjrCMyXMRD9qM4CzDj9ZNC-VtceL8oZgS8VRpebrIWjDdm1Ym7JhIRvAHYJ5-s4VhF5L7kjph-56TNuot6Spl3AyPoeNSSnE5cJxzwxFtfono_naKTBz1trd8LEzJLKL49SAI9OCUNYMF-Zgqg)

After that we could try our own 3D design with the tools. I first misunderstood the assignment and tried to create something with a block.\
![](https://lh5.googleusercontent.com/Nbkio3BOgBl2hT618GVd7tT8zwMHBgXCa-nCuBe-37OW_heyYUju8izj39SToz-Qx07yJ0nE_FiauS3-s_n-bexKiuB_dp2yr3Svjij7aWnGF9mEcoP3yaok5_VEKZxbzIpNcl5F7nrRrehyYb46C1A)

After I understood the assignment I created this.![](https://lh3.googleusercontent.com/bgYOv8E8TqN6tKUDoj0LHUO47V48cmu6T_bemzRO66Tram-I7MpcMyMkGK_6lprDqnxgXKNV_wwCN6uRzDYbrgax58MphZeHLoX87vr_zmHkLWCIxdWcSLbsFNQG90HMPAtgUUGWdNs9OcyFdgPMBuo)

We also needed to make a robot arm.![](https://lh3.googleusercontent.com/pd4Jjuj67gazrvSxQEI0yLWNVu1fsrEfARFd7QB9GNZI_PnvNwvBepwvZdD7-MsXsEtpsSswectq4acJZ7AYBcXd7czN6Kf9w5u3_2uXw--bq4CTQ7JxyV4maY8lvZINkntoQ-dhb3jEfV1INDOIy9Y)

Day 5 (13 sept):
================

Here we learned how to search and download stl files. And that is basically a base that we can use when designing something. That way we wouldn't have to start from scratch while designing something. We learned how to import that file and what we should keep in mind while 3D printing.

Day 6 (14 sept):
================

We saw examples of documentations and we needed to work on a robot arm in the session. I tried importing files from the internet to start it up. But I couldn't put the pieces back together.

Day 7 ( 26 sept):
=================

objective :  Recap from the trial period.

Coding of 2 DC motors.

HandsOn:

![](https://lh5.googleusercontent.com/HPNj6HFNdojiW3dHV6x9qNJxJ3aHHnHwNfQ74iKgsWRJ8PkPLjE2gpkzGrV8xDzi0k7QCYvbGAeM85zJoeiTAPsogqKaH4xjlWOka8ityTRaF-U90ePuBti_U-z5to6_JceWtTY5_Lk3J228zFFVdRc)

We had already built the 2 DC motors. We went in detail about the coding and learnt some new coding, how you can control your DC motors with bluetooth by putting a command in the serial monitor.

Code:

int motor1enable = 3;

int motor1input1 = 2;

int motor1input2 = 4;

int motor2enable = 5;

int motor2input1 = 7;

int motor2input2 = 8;

void motorforward()

{

  analogWrite(motor1enable, 255);

  digitalWrite(motor1input1, HIGH);

  digitalWrite(motor1input2, LOW);

  analogWrite(motor2enable, 255);

  digitalWrite(motor2input1, HIGH);

  digitalWrite(motor2input2, LOW);

}

void motorbackward()

{

  analogWrite(motor1enable, 255);

  digitalWrite(motor1input1, LOW);

  digitalWrite(motor1input2, HIGH);

  analogWrite(motor2enable, 255);

  digitalWrite(motor2input1, LOW);

  digitalWrite(motor2input2, HIGH);

}

void motorleft()

{

  analogWrite(motor1enable, 255);

  digitalWrite(motor1input1, LOW);

  digitalWrite(motor1input2, LOW);

  analogWrite(motor2enable, 255);

  digitalWrite(motor2input1, LOW);

  digitalWrite(motor2input2, HIGH);

}

void motorright()

{

  analogWrite(motor1enable, 255);

  digitalWrite(motor1input1, HIGH);

  digitalWrite(motor1input2, LOW);

  analogWrite(motor2enable, 255);

  digitalWrite(motor2input1, LOW);

  digitalWrite(motor2input2, LOW);

}

void motorstop()

{

  analogWrite(motor1enable, 255);

  digitalWrite(motor1input1, LOW);

  digitalWrite(motor1input2, LOW);

  analogWrite(motor2enable, 255);

  digitalWrite(motor2input1, LOW);

  digitalWrite(motor2input2, LOW);

}

int state;

void setup()

{

  Serial.begin(9600);

  pinMode(motor1enable, OUTPUT);

  pinMode(motor1input1, OUTPUT);

  pinMode(motor1input2, OUTPUT);

  pinMode(motor2enable, OUTPUT);

  pinMode(motor2input1, OUTPUT);

  pinMode(motor2input2, OUTPUT);

}

void loop()

{

  if (Serial.available() > 0){

  state = Serial.read();

  }

  if (state == 'F'){

    Serial.println("Forward");

    motorforward();  

  }

  else if (state == 'B'){

    Serial.println("Backward");

    motorbackward();

  }

  else if (state == 'R'){

    Serial.println("Left");

    motorright();

  }

  else if (state == 'L'){

    Serial.println("Left");

    motorleft();

  }

  else {

    Serial.println("Stop");

    motorstop();

  }

}

Mistakes: 

I made some coding errors, but when I saw my errors in the serial monitor I corrected them.

Day 8 ( 27 sept):
=================

objective :  Using an ultrasonic sound sensor and combining it in different circuits.

HandsOn:

![](https://lh6.googleusercontent.com/XQY3UU9_uqq6fgPNlT9tHeh-7o1lB20U0_L-aoAasN_1cgRke69DtgVh3lPW5ZBO1PzgfnDRxpzjUhM6cGlMxhTouw1_F5Gesbv1bYtvnTh3cITI6AERnq3NBYOttOvUC2LLBhXxM_AhtaFpOJR2_to)

Here we used the ultrasonic sound sensor to detect the distance and if we used conditions to program the servo motor.

Code:

#include <Servo.h>

#define echoPin 2

#define trigPin 3

Servo myservo;

long duration;

int distance;

int servoPin = 4;

void setup()

{

  pinMode(trigPin, OUTPUT);

  pinMode(echoPin, INPUT);

  myservo.attach(servoPin);

  Serial.begin(9600);

}

void detect()

{

  digitalWrite(trigPin, LOW);

  delayMicroseconds(2); 

  digitalWrite(trigPin, HIGH);

  delayMicroseconds(10);

  digitalWrite(trigPin, LOW);

  duration = pulseIn(echoPin, HIGH);

  distance = duration * 0.034 / 2;

  Serial.print("Distance: ");

  Serial.print(distance);

  Serial.println("cm");

}

void servo()

{

 if (distance < 50){

  myservo.write(90);

  }

  else if (distance > 50){

  myservo.write(180);

  }

}

void loop()

{

  detect(); 

  servo();  

}

![](https://lh6.googleusercontent.com/aMOQaNgCQslgWSYQlLbdqW-QP0XiEc_w91zGLBF99U6BCOgEcri707yR5CfoIDvxWsmi8n2P5MO2qM5aYNoY3GrilDLF3KCL1F5j25MW5lLvQR0Edp5A0EPijjsGwDZ7fEY7_F8H0tWlQJJ68imnAO4)

After that we put it together with 2 dc motors.

Code:

#include <Servo.h>

#define echoPin 6

#define trigPin 9

Servo myservo;

int motor1enable = 3;

int motor1input1 = 2;

int motor1input2 = 4;

int motor2enable = 5;

int motor2input1 = 7;

int motor2input2 = 8;

int state;

long duration;

int distance;

int servoPin = 10;

void motorforward()

{

  analogWrite(motor1enable, 255);

  digitalWrite(motor1input1, HIGH);

  digitalWrite(motor1input2, LOW);

  analogWrite(motor2enable, 255);

  digitalWrite(motor2input1, HIGH);

  digitalWrite(motor2input2, LOW);

}

void motorbackward()

{

  analogWrite(motor1enable, 255);

  digitalWrite(motor1input1, LOW);

  digitalWrite(motor1input2, HIGH);

  analogWrite(motor2enable, 255);

  digitalWrite(motor2input1, LOW);

  digitalWrite(motor2input2, HIGH);

}

void motorleft()

{

  analogWrite(motor1enable, 255);

  digitalWrite(motor1input1, LOW);

  digitalWrite(motor1input2, LOW);

  analogWrite(motor2enable, 255);

  digitalWrite(motor2input1, LOW);

  digitalWrite(motor2input2, HIGH);

}

void motorright()

{

  analogWrite(motor1enable, 255);

  digitalWrite(motor1input1, HIGH);

  digitalWrite(motor1input2, LOW);

  analogWrite(motor2enable, 255);

  digitalWrite(motor2input1, LOW);

  digitalWrite(motor2input2, LOW);

}

void motorstop()

{

  analogWrite(motor1enable, 255);

  digitalWrite(motor1input1, LOW);

  digitalWrite(motor1input2, LOW);

  analogWrite(motor2enable, 255);

  digitalWrite(motor2input1, LOW);

  digitalWrite(motor2input2, LOW);

}

void detect()

{

  digitalWrite(trigPin, LOW);

  delayMicroseconds(2); 

  digitalWrite(trigPin, HIGH);

  delayMicroseconds(10);

  digitalWrite(trigPin, LOW);

  duration = pulseIn(echoPin, HIGH);

  distance = duration * 0.034 / 2;

  Serial.print("Distance: ");

  Serial.print(distance);

  Serial.println("cm");

}

void dcmotor()

{

if (Serial.available() > 0){

  state = Serial.read();

  }

  if (state == 'F'){

    Serial.println("Forward");

    motorforward();  

  }

  else if (state == 'B'){

    Serial.println("Backward");

    motorbackward();

  }

  else if (state == 'R'){

    Serial.println("Right");

    motorright();

  }

  else if (state == 'L'){

    Serial.println("Left");

    motorleft();

  }

  else {

    Serial.println("Stop");

    motorstop();

  }

}

void servo()

{

 if (distance < 50){

  myservo.write(90);

  }

  else if (distance > 50){

  myservo.write(180);

  }

}

void setup()

{

  pinMode(echoPin, INPUT);

  pinMode(trigPin, OUTPUT);

  myservo.attach(servoPin);

  Serial.begin(9600);

  pinMode(motor1enable, OUTPUT);

  pinMode(motor1input1, OUTPUT);

  pinMode(motor1input2, OUTPUT);

  pinMode(motor2enable, OUTPUT);

  pinMode(motor2input1, OUTPUT);

  pinMode(motor2input2, OUTPUT);

}

void loop()

{

  detect();

  dcmotor();

  servo();

}

Mistakes: 

I made some coding errors, but when I saw my errors in the serial monitor I corrected them.

Day 9 ( 28 Sept) LAB:
=====================

objective :  Building the circuits that we have on thinkercad

Hands On :

First we made a circuit with 3 LED's. We used an arduino to make them blink. We also used resistors, so that the LED's don't break. 

![](https://lh3.googleusercontent.com/R4NoS_mEi_4i3pxoDxuY7tJkndd4NeNfIzEw2mHDubEd_OktcmMqWW_wwoQr3Ns8NAvoSGMBw9uUmd-GyEQx8ZmE6qJJ_2Exciw4PFBg4bwiT5gJ3FuoQU5b0vz5lzUouPP65CWumrDVg0-dBcYpARE)

Code:

int LED1 = 2;

int LED2 = 3;

int LED3 = 4;

void setup() {

  pinMode(LED1, OUTPUT);

  pinMode(LED2, OUTPUT);

  pinMode(LED3, OUTPUT);

}

void loop() {

  digitalWrite(LED1, HIGH);

  delay(250);

  digitalWrite(LED1, LOW);

  delay(250);

  digitalWrite(LED2, HIGH);

  delay(250);

  digitalWrite(LED2, LOW);

  delay(250);

  digitalWrite(LED3, HIGH);

  delay(250);

  digitalWrite(LED3, LOW);

  delay(250);

}

After this we made another circuit with a push button in it. The pushbutton isn't really visible in the picture. We used it to make the LED's blink. 

![](https://lh3.googleusercontent.com/rJ8v4IBViAzdrTVQP6d1EUt6hdvVb-N6Kxz6UepFVziqSQ10I0NEVL8VPFbzB8-X6DufI4gm-mv3NUDOMn4eTYRUM4XhdC7sIGdhusqBKtBl7YtjV_wYwOrNwIczeF_J7GzjXqJpZPlhyj_flM9FptE)

Code:

int LED1 = 2;

int LED2 = 3;

int LED3 = 4;

int button = 5;

void setup() {

pinMode (LED1, OUTPUT);

pinMode (LED2, OUTPUT);

pinMode (LED3, OUTPUT);

pinMode (button,INPUT);

}

void loop() 

{

 if (digitalRead(button) == HIGH)

{

  digitalWrite (LED1, HIGH);

  delay(200);

  digitalWrite (LED1, LOW);

  delay(200);

  digitalWrite (LED2, HIGH);

  delay(200);

  digitalWrite (LED2, LOW);

  delay(200);

  digitalWrite (LED3, HIGH);

  delay(200);

  digitalWrite (LED3, LOW);

  delay(200);

}

 else

{

  digitalWrite(LED1, HIGH);

  digitalWrite(LED2, HIGH);

  digitalWrite(LED3, HIGH);

}

}

After that we used a potentiometer to control the LED's. This didn't quite work yet. We used different potentiometers, but still. 

![](https://lh5.googleusercontent.com/cCjvq_MKBye7VEyxsEeVQzJ_N9aJoXH-qHxcdoRD_rfLmzEzlmCHhYPkoIRzHeRmpF2tvE7rmUnulc24SMTmhWRjxrQ9aCh-KraVkb3OokjmdFVZsk7XXRJW2akmRr0pRXSE8TNcU-v5Lq0mY9mwJ54)

Code :

int LED1 = 2;

int LED2 = 3;

int LED3 = 4;

int pot = A0;

void setup() {

  Serial.begin(9600);

  pinMode(LED1, OUTPUT);

  pinMode(LED2, OUTPUT);

  pinMode(LED3, OUTPUT);

}

void loop(){

  int pot_value = analogRead(pot);

  Serial.println(pot_value);

  int LED_value = map(pot_value, 0, 1023, 0, 255);

  digitalWrite(LED1, LED_value);

//  digitalWrite(LED2, LED_value);

//  digitalWrite(LED3, LED_value);

}

Day 10 ( 3 october):
====================

objective :  Introduction to multitasking

Hands On :

First we made LED's blink with delays. The code is in the picture below.

![](https://lh4.googleusercontent.com/ya2P6t0Rr5uFcg52wgXuZ359-N_OLp34m2FgYRGNukEYNRe2u4RaZBGI_ajLYl4s0UOSeodeyuvAuBucqkej7synGXkw_-OP8OolZkshGhPZCOAMYPszQXP1_dEnUT7qQI-raJETl7eAl3HgY6ZOb7Y)

Then we tried to do the same but with the function millis. Millis is basically a timer for the arduino. As soon as the arduino gets power, the timer starts. 

We also used a different statement for HIGH and LOW, we just used an " !digitalRead(LED) ". That means it does the opposite of what the LED is doing now. We used if statements to turn the LED's on and off. And the condition for the if statement was that the difference in the arduino-timer and the time the LED was last changed should be the delay. And in the statement we update the time the LED was last changed.

The code:

int LED = 2;

int LED2 = 11;

int LED3 = 10;

int redDelay = 500;

unsigned long redLastChanged = 0;

int greenDelay = 250;

unsigned long greenLastChanged = 0;

int yellowDelay = 333/2;

unsigned long yellowLastChanged = 0;

void setup()

{

  pinMode(LED, OUTPUT);

  pinMode(LED2, OUTPUT);

  pinMode(LED3, OUTPUT);

  Serial.begin(9600);

}

void updateRedLed()

{

if (millis() - redLastChanged >= redDelay)

  {

  digitalWrite(LED, !digitalRead(LED));

  redLastChanged = millis();

  Serial.print("Red:");

  Serial.println(redLastChanged);

  }

}

void updateGreenLed()

{

  if (millis() - greenLastChanged >= greenDelay)

  {

  digitalWrite(LED2, !digitalRead(LED2));

  greenLastChanged = millis();

  Serial.print("Green:");

  Serial.println(greenLastChanged);

  }

}

void updateYellowLed()

{

  if (millis() - yellowLastChanged >= yellowDelay)

  {

  digitalWrite(LED3, !digitalRead(LED3));

  yellowLastChanged = millis();

  Serial.print("Yellow:");

  Serial.println(yellowLastChanged);

  }

}

void loop()

{

 updateRedLed();

 updateGreenLed();

 updateYellowLed();

}

Day 11 ( 4 october):
====================

objective :  Introduction to multitasking

Hands On :

We made a LED blink in a second, and after that we connected a servo motor to turn 180 degrees while it blinks. 

![](https://lh6.googleusercontent.com/2671u5ws2nH2kQJ9vACzfu4Y36JtdZJynLVQsY2wrg2rVTbA1nISLeWs0RLYo1YtuMtwc6cJVHiZCW54LYXZdd0Znn-4AWdP5szOfpIsyu7aNU1ksGNnWCsbd0XLx8HfratcPvOY2Dapl--FCCtkzzM)

The code:

#include <Servo.h>

int redLed = 2;

int servoPin = 6;

int redDelay = 1000;

int servoDegree = 0;

unsigned long redLastChanged = 0;

Servo myservo;

void setup()

{

  pinMode(redLed, OUTPUT);

  myservo.attach(servoPin);

  Serial.begin(9600);

}

void loop()

{

  if (millis() - redLastChanged >= redDelay)

  {

    digitalWrite(redLed, !digitalRead(redLed));

    redLastChanged = millis();

    Serial.print("Red:");

    Serial.println(redLastChanged);

    if (servoDegree == 0)

    {

      servoDegree = 180;

      myservo.write(servoDegree);

      Serial.println(servoDegree);

    }

    else if (servoDegree == 180)

    {

      servoDegree = 0;

      myservo.write(servoDegree); 

      Serial.println(servoDegree);

    }

  }  

}

Day 12 ( 5 october) LAB:
========================

objective :  Building  2 DC motors.

Adding a ultrasonic sound sensor.

Adding a servomotor.

Hands On :

First we made a schematic of 2 DC motors and then we connected them to the arduino and wrote a code for that. We made a schematic because all the wires would be difficult to follow if we didn't make one. 

![](https://lh5.googleusercontent.com/9NjrBtKMSDPzVD5WEDJbXATZ4qAlkCoW-WevUNdhFjDdbosezB2HJYciHtwaKw3Xm9eIdskM0WFmMPQB5VkS9wOztr8AQUw3h4W_2UmlsesjCaD7mgOWqpC-6dfsa442ERUGVMubxEOIq87JwsfboUM)

After that we put an ultrasonic sound device in it to detect objects and also coded it. 

![](https://lh5.googleusercontent.com/9tjGaMNAnDybgzcQq0nKmJkmF4h1HJgqysX3TbPz_JR5h6u8hmzKfu4RGgOG7qyvhpd9WcVnW9qwHnD4FnLVdYmJYV_xnoUhNJWFAmmONri1113cHdMnfs3TKDg-KdYtxef2j12wMGvwSiMHmfzWp9U)

Then we put the final thing, that was an servo motor. And we coded it so that it would move whenever the ultrasonic sound device would detect something. 

![](https://lh5.googleusercontent.com/HaFFFrLVRryq4_QlctjH2vSQjrAMPvPOTM2wSx3Hk2WHKyYfvohtjfp8rsxKi6PJoSooW2YoAAC2-xYvxJz3Xo2fIPgS0kWdTfC2In5QaZ0vDo88KccmX5CUNHmvWx6G3mrybCkS3V_QTnqlbZCHGqE)

The final code was:

#include <Servo.h>

#define echoPin 10

#define trigPin 9

Servo brunoServo;

int motor1enable = 3;

int motor1enable2 = 5;

int motor1input1 = 2;

int motor1input2 = 7;

int motor1input3 = 8;

int motor1input4 = 4;

long duration;

int distance;

int servoPin = 11;

int state;

void motorforward()

{

  analogWrite(motor1enable, 255);

  digitalWrite(motor1input1, HIGH);

  digitalWrite(motor1input2, LOW);

  analogWrite(motor1enable2, 255);

  digitalWrite(motor1input3, HIGH);

  digitalWrite(motor1input4, LOW);

}

void motorbackward()

{

  analogWrite(motor1enable, 255);

  digitalWrite(motor1input1, LOW);

  digitalWrite(motor1input2, HIGH);

  analogWrite(motor1enable2, 255);

  digitalWrite(motor1input3, LOW);

  digitalWrite(motor1input4, HIGH);

}

void motorleft()

{

  digitalWrite(motor1input1, LOW);

  digitalWrite(motor1input2, LOW);

  digitalWrite(motor1input3, LOW);

  digitalWrite(motor1input4, HIGH);

}

void motorright()

{

  digitalWrite(motor1input1, HIGH);

  digitalWrite(motor1input2, LOW);

  digitalWrite(motor1input3, LOW);

  digitalWrite(motor1input4, LOW);

}

void motorstop()

{

  digitalWrite(motor1input1, LOW);

  digitalWrite(motor1input2, LOW); 

  digitalWrite(motor1input3, LOW);

  digitalWrite(motor1input4, LOW);

}

void detect()

{

  digitalWrite(trigPin, LOW);

  delayMicroseconds(2); 

  digitalWrite(trigPin, HIGH);

  delayMicroseconds(10);

  digitalWrite(trigPin, LOW);

  duration = pulseIn(echoPin, HIGH);

  distance = duration * 0.034 / 2;

  Serial.print("Distance: ");

  Serial.print(distance);

  Serial.println("cm");

}

void servo()

{

 if (distance < 50){

  brunoServo.write(90);

  }

  else if (distance > 50){

  brunoServo.write(180);

  }

}

void setup()

{

  Serial.begin(9600);

  pinMode(motor1enable, OUTPUT);

  pinMode(motor1input1, OUTPUT);

  pinMode(motor1input2, OUTPUT);

  pinMode(motor1enable2, OUTPUT);

  pinMode(motor1input3, OUTPUT);

  pinMode(motor1input4, OUTPUT);

  pinMode (trigPin, OUTPUT);

  pinMode (echoPin, INPUT);

  brunoServo.attach(servoPin);

}

void loop()

{

  detect();

  if (Serial.available() > 0){

  state = Serial.read();

  }

  if (state == 'F'){

      Serial.println("Forward");

      motorforward();

  }

  else if (state == 'B'){

      Serial.println("Backward");

      motorbackward();

  }

   else if (state == 'L'){

      Serial.println("Left");

      motorleft();

  }

  else if (state == 'R'){

      Serial.println("Right");

      motorright();    

  }

   else if  (state == 'S'){

      Serial.println("Stop");

      motorstop();

  }

  else {

  Serial.println("Input Command");

  }

  servo();

}

After this we tried to control it with our mobile with the use of an app "Bluetooth Electronics"

Day 13 ( 11 october):
=====================

objective :  Using the internet as a source to work with a buzzer.

Hands On :

I used this link to research. You have different melodies also, but I just coded a buzzer that just goes on and off and the code for it is in the picture. 

<https://create.arduino.cc/projecthub/SURYATEJA/use-a-buzzer-module-piezo-speaker-using-arduino-uno-89df45>

![](https://lh3.googleusercontent.com/YedHqZLilq9smzhJVOIoMiDXrMOk9tSQ7ul5B5pjv3NusLcd73ElaGAjTGvtNcXB8T8ofeL7kwzOMYPL6iCd5LjX82XSFku4ekXZFaV_A-JOYielC6hcnXfN5aRwCzdpZnTMTJYgFL7yMqlqBU5bak4)

Day 14 ( 17 october):
=====================

objective :  A sketch of the design of the rover.

Learning the self-driving part.

HandsOn:

![](https://lh4.googleusercontent.com/bkwWC7uKZVphS0WHxvEoR5fxysskoA_M1hTj5Lv2Al3-dMjfn7h4iPanR7lem7z7LVu34ZUG1U3qckM2gd5d0DY3NpioCkm__14oALUbr4jkFJWpfK4o84NcP8SYWlWEAXjI7vvOX7AuZUiVF7JFKI8)

This is a sketch of our rover. It takes up trash and puts it in a trash bin that opens. 

Day 15 ( 18 october):
=====================

objective :  A sketch of the design of the rover with the parts.

Making a circuit for the extra features. 

HandsOn:

![](https://lh4.googleusercontent.com/AcAiwfT6e88G13jde7WP5-Uz4Xcn3bFfiOoXZoPOL_zZnivgedr4be9d0BSgKjXKFTw4PxY6Gc_moqignBjWcpRF798ZSWJvH5o9iOsuEOQAWM615TS9QchUiM2pU5Yil4Lxo9JpDwrC4ppW9mlP6O4)

First we thought to have 4 servo motors to control the arm, but the pins would be a problem, so we settled on 3 (unlike the sketch above).

![](https://lh3.googleusercontent.com/TrLqZFQpDJrIJZ9FYWjIJUgIx0wjb2WVjCqGMSKn1hrLNrtIzSYz2t5SEwY_SndG6zQYxSsAYFgWy0IMMBID9pIuL8UHAMZusx3z6JFi9DRZOwQ8XGs61coZBKknrKrPIvzCF0VEO5ArgVsnuSmQE_8)

Code: https://www.tinkercad.com/things/iQOgqfT3Hni-shiny-jaagub-amur/editel?sharecode=0KZkNzfYGNxjzj-ozrpAj644477yFsqnLJLxYPbaW60

Day 16 ( 19 october) LAB:
=========================

objective :  A sketch of the design of the rover with the parts.

Making a circuit for the extra features. 

HandsOn:

We made our first design with cardboard.

![](https://lh6.googleusercontent.com/iOThZfA_UOILKxy0moEOl03R2UQ6FPnsfHxBImzDVa8rVBZaP1Z7qe-Lg3TvVflaFkAMO0h30UhcOdjbZBAbgeyp1u0btX9FV7i8YsDxcVHwjv3_TYlN0OmBbQF6sLEp_vC_GAT18fFmMLf4__t4WSU) 

This was just a regular rover without the additional features. It could only ride with bluetooth.

Inside we have a different arduino nano and a motor driver and also some batteries.  

![](https://lh4.googleusercontent.com/vForlpVdRsRm82Yo8pcjq69ZgAH_wrBY8rljdERDxy43-xHIrGcrzYRW3JAFm7Hr_5E5NN3fobOpvhK2l9aR0Mu1PC6GQ95lLc6rqsmKBLig9hom74ehL2YMs6NJARPhf6y8XjsNFfOsyi4KIB3tra8)

This is a schematic of the pins that we put in the rover.

Day 17 ( 26 october) LAB:
=========================

objective :  Concentrating on little details from the rover.

Programming its arm.

HandsOn:

We tried exploring more with the rover. We put a servo motor on the ultrasonic distance sensor so that it could detect objects. We did not code it to maze yet. 

![](https://lh4.googleusercontent.com/Rxf-T2_gFIhgBWZ-i8OngcIQFvmmLun2J0SocEE5oq5E_CoQmM60UKPrgmi0UT4FEDEDlckcUX4cY1MqbjY2wPVqoc06D2ayGdtMnN98NOSsM5zb7fdKBfcBOFmE644xQwRIggnkEbu2klP-src_iIk)

![](https://lh4.googleusercontent.com/k4gJu1aSQe-8_5iTQyFtE4K6WLOYevyoifCMHwr4OrxgN8O2KVxawmTdCGXwPS_1INk8lYp2XmOM_L0xokanqhKZYgNHQoYu0C2WSgsvonDcaOXWv8kNpUizrqE6ns8hL3o9gjipZ1-9Z2WEQwfjf2k)
==============================================================================================================================================================================================

The code for the robot arm with 3 servomotors and 1 extra for the bin:

#include <Servo.h>

#define trigPin 6

#define echoPin 7

Servo servoTrash;

Servo servoRotate;

Servo servoGrip;

Servo servoHeight;

int servoPin1 = 1;

int servoPin2 = 2;

int servoPin3 = 3;

int servoPin4 = 4;

int duration;

int distance;

int state;

void trashcan()

{

  digitalWrite(trigPin, LOW);

  delayMicroseconds(2); 

  digitalWrite(trigPin, HIGH);

  delayMicroseconds(10);

  digitalWrite(trigPin, LOW);

  duration = pulseIn(echoPin, HIGH);

  distance = duration * 0.034 / 2;

  if (distance < 5)

  {

    servoTrash.write(90);

    delay(1000);

    servoTrash.write(0);

  }

}

void setup()

{

  pinMode(trigPin, OUTPUT);

  pinMode(echoPin, INPUT);

  servoTrash.attach(servoPin4);

  servoRotate.attach(servoPin3);

  servoGrip.attach(servoPin2);

  servoHeight.attach(servoPin1);

  Serial.begin(9600);

}

void loop()

{

   if (Serial.available() > 0)

    {

     state = Serial.read();

    }

  if (state == 'P')

  {

    servoGrip.write(90);

    servoHeight.write(45);

    servoRotate.write(180);

    trashcan();

    servoGrip.write(0);

    servoRotate.write(0);

  }

}

Day 18 ( 1 november):
=====================

objective :  We asked for help to make the robot arm. 

<https://www.electronicshub.org/bluetooth-controlled-servo-motor-using-arduino/>

<https://maker.pro/arduino/tutorial/how-to-control-servo-motors-android-app-smart-device-arduino-uno-bluetooth>

We were suggested to look for examples on these links. We saw sliders in one of them and thought it was a good idea. There was another alternative, but the programming would take a little more time to do. So we decided to try the sliders in the lab.

Day 19 ( 2 november) LAB:
=========================

objective :  Making  the real rover.

Programming its sliders for the arm.

HandsOn:

We made our original base (not from cardboard) and we tested the slider code but it didn't work. So we got another code for the sliders.

Code for the sliders: 

#include <SoftwareSerial.h> 

#include <Servo.h>

Servo servo1; 

Servo servo2;

Servo servo3;

int servoPin1 = 4;

int servoPin2 = 3;

int servoPin3 = 2;

int TX = 10; 

int RX = 11;

SoftwareSerial HC_05(TX, RX);

void setup()

{

  servo1.attach(servoPin1); 

  servo2.attach(servoPin2);

  servo3.attach(servoPin3);

  Serial.begin(9600);

  HC_05.begin(9600);

}

void loop()

{

  if(HC_05.available()> 0 ) 

  {

    int value = HC_05.read(); 

    if(value>=0 && value<=90)

    {

      Serial.println(value); 

      int servo1_position = map(value, 0, 90, 0, 180);

      servo1.write(servo1_position);

    }

   if(value>90 && value<=180)

   {

      Serial.println(value); 

      int servo2_position = map(value, 91, 180, 0, 100);

      servo2.write(servo2_position);

    }

    if(value>180 && value<=270)

   {

      Serial.println(value); 

      int servo3_position = map(value, 181, 270, 0, 180);

      servo3.write(servo3_position);

    }

  }

}

Day 20 ( 9 november) LAB:
=========================

objective :  Trying to make the maze part work.

Assembling its arm.

HandsOn:

We made a part of the arm using this link:

<https://www.electronicshub.org/robotic-arm/#Step_1>

![](https://lh4.googleusercontent.com/R_E4qX_k78RnUsqyJCMccNZh1BFxmw5qTxPOc1qnQ8zGbr7LL13_tnqc2vtvbrIB-q6JLhDHtP8nf2m89ku8FWrxxupnqWNso-klS85awjZJTFl-tfzg0FnJbU3TD7iOy8FitZpfWSWtYncL_VjyL38)

  ![](https://lh5.googleusercontent.com/xUc9ZpmJ0Y_4RkWBAf7RbCkPsOhu2ZzXRHIYMP7ce-kN8aaYdQktEfpW1ufWEoklpnbxK7XilplGq1uAwbm0dy72a8plGLSLFQaZwG_b2_zu6xH3TOELSVMYChDOjINyxKylvYt1q3Cc1KjFvPM-awo)![](https://lh6.googleusercontent.com/5wSMmQBf8XCtDbIFr1Mf0R-o_Do7i4H5Bw46lWQOaFz31E4BYHX9RkWYg_K9PGwr520MJiWKjT15YD_Fg1mvCI1i-OGKH1mcxrlLTqS4ufYZKRQFnjOJmkrgR-oPaPH8aLNB3A6uIA2NdRwc-9enwdY)

Day 21 ( 16 november) LAB:
==========================

objective :  Programming the robot arm.

We used a code for sliders. But it wasn't working yet. Only one of the 3 servo's were working at a time. We tried bugging the code but still. The slider method wasn't working because too much information was being sent.

Code(before we costumized it):

//Nurlan Quluzade

#include <SoftwareSerial.h>

#include <Servo.h> // servo library 

Servo myservo1, myservo2, myservo3, myservo4; // servo name

//int bluetoothTx = ;

//int bluetoothRx = 1;

//

//SoftwareSerial bluetooth(bluetoothTx, bluetoothRx);

void setup()

{

  myservo1.attach(6);

  myservo2.attach(3);

  myservo3.attach(5);

  myservo4.attach(9);

  //Setup usb serial connection to computer

  Serial.begin(9600);

  //Setup Bluetooth serial connection to android

  //bluetooth.begin(9600);

}

void loop()

{

  //  if(Serial.available()>= 2 ) //if(bluetooth.available()>= 2 )

  //  {

      unsigned int realservo;

  ////    unsigned int servopos1 = Serial.read();

  ////    unsigned int realservo = (servopos1 *256) + servopos;

  //    Serial.println(realservo);

  while (Serial.available()==0) {}     //wait for data available

  String rcvStr = Serial.readString();  //read until timeout

  rcvStr.trim();                                     // remote \r \n and spaces

  realservo= rcvStr.toInt();                        // Cast input into Integer (if it fails => realservo = 0

  // Debugging

  Serial.print("Rcv : ");

  Serial.print(rcvStr);

  Serial.print(" int -> ");

  Serial.println(realservo);

  if (realservo >= 1000 && realservo < 1180) {

    int servo1 = map(realservo, 1000, 1179, 0, 179);

    myservo1.write(servo1);

    Serial.print("Servo 1 -> ");

    Serial.println(servo1);

    delay(15);

  }

  if (realservo >= 2000 && realservo < 2180) {

    int servo2 = map(realservo, 2000, 2179, 0, 179);

    myservo2.write(servo2);

    Serial.print("Servo 2 -> ");

    Serial.println(servo2);

    delay(15);

  }

  if (realservo >= 3000 && realservo < 3180) {

    int servo3 = map(realservo, 3000, 3179, 0, 179);

    myservo3.write(servo3);

    Serial.print("Servo 3 -> ");

    Serial.println(servo3);

    delay(15);

  }

  if (realservo >= 4000 && realservo < 4180) {

    int servo4 = map(realservo, 4000, 4179, 0, 179);

    myservo4.write(servo4);

    Serial.print("Servo 4 -> ");

    Serial.println(servo4);

    delay(15);

  }

}

Day 22 ( 30 november) LAB:
==========================

objective :  Programming the robot arm again. 

The arm still wasn't working so we left the sliders out and tried something different. And it worked. Now our challenge was to write a more general code for this. 
===================================================================================================================================================================

This was the code:

#include <Servo.h>

Servo servoEndEffector;

Servo servoBase;

Servo servoElbow;

int servoPin1 = 13; // end effector

int servoPin2 = 2; // base servo

int servoPin3 = 3; // elbow

int TX = 0;

int RX = 1;

void setup()

{

  servoEndEffector.attach(servoPin1);

  servoBase.attach(servoPin2);

  servoElbow.attach(servoPin3);

  Serial.begin(9600);

}

void moveX (int dir)

{

  int stepSize = 10;

  int newPos = servoBase.read() + stepSize * dir;

  if (newPos > 179)

  {

    servoBase.write(179);

  }

  else if (newPos < 0)

  {

    servoBase.write(0);

  }

  else

  {

    servoBase.write(newPos);

  }

}

void moveY (int dir)

{

  int stepSize = 10;

  int newPos = servoElbow.read() + stepSize * dir;

  Serial.println(servoElbow.read());

  if (newPos > 179)

  {

    servoElbow.write(179);

  }

  else if (newPos < 0)

  {

    servoElbow.write(0);

  }

  else

  {

    servoElbow.write(newPos);

  }

}

void moveZ (int dir)

{

  int stepSize = 10;

  int newPos = (stepSize * dir) + servoEndEffector.read() ;

  // Serial.println(newPos);

  if (newPos > 179)

  {

    servoEndEffector.write(179);

  }

  else if (newPos < 0)

  {

    servoEndEffector.write(0);

  }

  else

  {

    servoEndEffector.write(newPos);

  }

}

void loop()

{

  if (Serial.available() > 0 )

  {

    int state = Serial.read();

    if (state == 'X') {

      moveX (1);

    }

    else if (state == 'x') {

      moveX (-1);

    }

    if (state == 'Y') {

      moveY (1);

    }

    else if (state == 'y') {

      moveY (-1);

    }

    if (state == 'Z') {

      moveZ (1);

    }

    else if (state == 'z') {

      moveZ (-1);

    }

  }

}

Day 23 ( 7 december) LAB:
=========================

objective : Using the code for the robot arm.

Last week we got a code for our robot arm. We tested it and we had some problems with the zeroth position of the servomotors. So we fixed that. Also we needed a default position for our robot arm, because it needed a lot of power. The battery quickly became empty. 

Day 24 ( 14 december) LAB:
==========================

objective : Customizing the robot arm.

We built the robot arm from a plastic container. We carved out the pieces that we needed. And we connected it with servo motors, so that it would move when we commanded it via bluetooth.

Still we weren't done with the robot arm.

![](https://lh4.googleusercontent.com/T8C-w0zwfGKIA75HBCA86GrXiExtty_hyldZsiBvu9J61jQGX6_kx4yUgYD4ubsrCToYEbFnXDep7DNRiRv67GeITACvFJruuIOg_5cxtxh7-hVEKLs2Na-ZT5dmDZEdNd2VaLTtS9QadlsA2iJfvXU)![](https://lh4.googleusercontent.com/edKsaD74L3V8g8uWN9q4t0jzNrifxKzpt-kH6BLvqtkt_rvwUCl7G3Jp17cTeeb4sO3Jjnt5pkNbtBBNufQlP1RWoFPVf7qhJT4hz4Sz3JyPY4cJFep5OAwFdR2CpqQyBUkxr3y5iXtbRMkmkThyNgY)

Day 25 ( 18 januari) LAB:
=========================

objective : Testing the rover.

The rover was fully customized. Only thing left to do was test it.

![](https://lh5.googleusercontent.com/AxxsD-BHG18NJWFdWsxKuWqOOuCW2y_W1QddvVtfv5NxaeKcgxEuut6oYn3rfwSE_JpGHlzh7TFErm43gl2zpcTLmgfKLx8MDbeCjqPjOk_mzLcKC9Bxj4UgOHA0rP19dg8q58jvAdIEcycBS3rK7Cg)

![](https://lh5.googleusercontent.com/UOUGi3LHGYKDCCziTu_AXKHnlksLPBMhOk38tAm_JGwLa2lDi5ePTfkwqAWhejzKd-hDx8aq1qlVUYMq3VIImnZ70eTdAURzddb6VtTYjHjnupNh4VqbfOjDWdwjBn7Qzq_7P7iJazh0onHyeKw9Dh0)

![](https://lh6.googleusercontent.com/oJvSRChW8cOqdIqrKmQFJzCH0M4HDGtenFQXRS5R1v-dbsatfj63V_FE7AqsP8lVXdl1-PkG3sZWoonQT8Lgmq0jtB1kZPGZxYkDSDnrVbMvNOuo86yHGE1H9Uc1odEsudtO6u-wxW855xUfQ0YZT74)

![](https://lh4.googleusercontent.com/a5pI91SYdKo-vMw6JcTfibFlGcL9a1MRuj-BYzFYUyIMnQR3xTEg_8Zgr8RnCRMbgg_mxjOBWwFDcCXarWf-Wi_5x0YZV_poVvrYmh4mcaEN5Sq3R_ORX5RUIDL5Pi_hja1tXldcmI46XF-TTdz1KO0)