/* Oswald Lawson
MSE2202B Practice Exam 2016
2020*/

#include <Servo.h>

// signal if there is a brake problem
const int ledRed = 7; 

// button that will be pressed while there is a problem
const int button = 8;

// vibrating motor to be used in some undetermined fashion
const int vMotor = 10;
const int servoPin = A1;

int buttonValue;

// servo controls the caliper
Servo caliper_control;


//timer variables
unsigned long ui_previous = 0;
int interval = 100;

int servo_position = 0;

void setup()
{
  caliper_control.attach(A1);
  pinMode(ledRed, OUTPUT);
  pinMode(button, INPUT);
  pinMode(vMotor, OUTPUT);
  caliper_control.write(170);
}

void loop()
{

  buttonValue = digitalRead(button);
  
  if(buttonValue == 1) {
    digitalWrite(ledRed, HIGH);
    
    if (millis() - ui_previous > interval)
  {
    servo_position = servo_position - 5;
    constrain(servo_position, 10, 170);
      
    caliper_control.write(servo_position);
    
    ui_previous = millis();
  }
  }
  
   else if (buttonValue == 0) {
    digitalWrite(ledRed, LOW);
    
    if (millis() - ui_previous > interval)
  {
    servo_position = servo_position + 5;
    constrain(servo_position, 10, 170);
      
    caliper_control.write(servo_position);
    
    ui_previous = millis();
  }
  }
  
} 
