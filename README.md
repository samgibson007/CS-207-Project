
#include <Servo.h>
const int sensorpin = 13;  
                           /* THIS IS THE PIN IN THE FUTURE THAT WILL READ WEATHER THERE IS A 
                              VOLTAGE THAT IS PASSING THROUGH THE SENSOR OR NOT AND WILL SUBSIQUENTLY 
                              TELL THE ARDUINO TO TURN THE SERVO ONE WAY AND STAY WHEN THERE IS A VOLTAGE 
                            ANS THEN THE OTHER WAY WHEN THERE IS NO VOLATEG.*/
                           

Servo myservo;  // create servo object to control a servo
// twelve servo objects can be created on most boards

int pos = 0;    // variable to store the servo position

void setup() {
  myservo.attach(9);  // attaches the servo on pin 9 to the servo object
  pinMode(sensorpin, INPUT);
}

void loop() 
{
  
  if(sensorpin == HIGH)
  {
    for (pos = 0; pos <= 180; pos += 1) 
    {
    myservo.write(pos);              
    }
  }
  
 if(sensorpin == LOW)
 {
  for (pos = 180; pos >= 0; pos -= 1) 
  { 
    myservo.write(pos);              
  }
  }
  
}



