# Railway-Automatic-Gate-Controlling-System 

This project is based on Hardware components like Arduino UNO, IR Sensors, Servo Motors, Toy Train etc. 

Source Code : 
#include <Servo.h>

Servo gate1_servo;
Servo gate2_servo;

int sensor1_pin = 4; 
int sensor2_pin = 5; 
int gate1_servo_pin = 6; 
int gate2_servo_pin = 7; 

int val1; 
int val2; 

void setup() {
  pinMode(sensor1_pin, INPUT);
  pinMode(sensor2_pin, INPUT);
  
  gate1_servo.attach(gate1_servo_pin);
  gate2_servo.attach(gate2_servo_pin);
  
  Serial.begin(9600);
}

void loop() {
  val1 = digitalRead(sensor1_pin);
  val2 = digitalRead(sensor2_pin);
  
  Serial.print("IR Sensor 1: ");
  Serial.print(val1);
  Serial.print("  IR Sensor 2: ");
  Serial.println(val2);
  
  if (val1 == 0 && val2 == 0) { 
    closeGates(); 
    delay(1700); 
  }
  else { 
    openGates(); 
  }
}

void closeGates() {
  gate1_servo.write(0); 
  gate2_servo.write(0); 
}

void openGates() {
  gate1_servo.write(90); 
  gate2_servo.write(90); 
}


For more details contact mahmudsabbir615@gmail.com or +8801704894937
