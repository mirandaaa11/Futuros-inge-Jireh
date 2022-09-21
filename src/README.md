Control software
====

This directory must contain code for control software which is used by the vehicle to participate in the competition and which was developed by the participants.

<h1 align="center"> Control software </h1>

#include <PWMServo.h>
#include <Servo.h>
#include <NewPing.h>

#include <PWMServo.h>
#define IN1 7
#define IN2 8
#define ENA 5        //  ENA pin

Servo steer;    //servomotor para direccionales
#define SERVO_PIN 9
 

 int dist_izq
 int dist_der
 int dist_front
 
#define FRONT 90        // steering to front 
int SHARP_RIGHT=FRONT+33;
int SHARP_LEFT=FRONT-40;

#define DELAY_TIME 1200     
#define BACK_TIME 1000  
#define SPEED 190
#define HI_SPEED 220
#define SERVO_PIN 9  //servo connect to D9


//sensor 3  DERECHO
int TRIG3_PIN = ;        //cambiar pin al de conexion actual
int ECHO3_PIN = ;        //cambiar pin al de conexion actual
//sensor 2 IZQUIERDO
int TRIG2_PIN = ; 
int ECHO2_PIN = ; 
//sensor 1 Dir_Frente
int TRIG1_PIN = ; 
int ECHO1_PIN = ; 


 

 
void  go_Advance(int speed)  //Forward
{
  digitalWrite(IN1, HIGH);
  digitalWrite(IN2,LOW); 
  analogWrite(ENA,speed);
 
}
 
void turn(int angle)
{

  head.write(angle);

}
 
void stop_Stop()    //Stop
{
  digitalWrite(IN1, LOW);
  digitalWrite(IN2,LOW);
  analogWrite(ENA,0);
 
}



NewPing SensorA1(TRIG1_PIN,ECHO1_PIN);
NewPing SensorA2(TRIG1_PIN,ECHO1_PIN);
NewPing SensorA3(TRIG1_PIN,ECHO1_PIN);

void Sensor_P(){  //mueve el sensor frontal en tres angulos
  
servoA.write(30);
   dist_recto=SensorA1.ping_cm();
  Serial.print (dist_recto);  
   Serial.print(" recto ");
     delay(500);

   servoA.write(190);
   dist_der= SensorA1.ping_cm();
   Serial.print (dist_der);
   Serial.print(" derecho ");
    delay(500);
   
   servoA.write(90);
   distizq= SensorA1.ping_cm();
   Serial.print (dist90);
   Serial.println("  izquierdo  " );
   delay(500);
}
Servo servoA

void predic()
{
  if (dist_der<25)
  {
    steer.write(75);
    delay(750);
   steer.write(100);
    delay(300);
    steer.write(FRONT);
    delay(200);
    
  }

    if (dist_der<25)
  {
    steer.write(105);
    delay(750);
  steer.write(70);
    delay(300);
    steer.write(FRONT);
    delay(200);
  }
  
}

void setup() {
 pinMode(ENA, OUTPUT); 
 pinMode(IN1, OUTPUT); 
 pinMode(IN2, OUTPUT);

smotorsen.attach(10,840,1870);
steer.attach(9,600,1250);

}

void loop() {
 go_Advance(190);
 predic();
 
 
 

}


<h1 align="center"> <h1 align="center"> The  artifacts required to resolve dependencies and build the project  </h1>
 
 ![No-page-0001.jpg](https://i.postimg.cc/pTgZw4yH/No-page-0001.jpg)
 
![No-2.png](https://i.postimg.cc/261p0JXY/No-2.png)
 
 ![No-page-0003.jpg](https://i.postimg.cc/CK79VhVV/No-page-0003.jpg)

 ![No-page-0004.jpg](https://i.postimg.cc/Qx58ZTYG/No-page-0004.jpg)
 
 
