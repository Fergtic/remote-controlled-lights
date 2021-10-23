#include <IRremote.h>

#include <Servo.h>

#define Button_1 0x1FE48B7

#define Button_1_1 0x1FE48B

#define Button_1_2 0x1FE48

#define Button_1_3 0x1FE4

#define Button_2 0x1FE58A7

#define Button_2_1 0x1FE58A

#define Button_2_2 0x1FE58

#define Button_2_3 0x1FE5

int RECV_PIN = 2;

uint32_t Previous;

IRrecv irrecv(RECV_PIN);

decode_results results;

Servo on_servo;

Servo off_servo;

void setup()

{

  Serial.begin(9600);

  on_servo.attach(8);

  off_servo.attach(9);

  irrecv.enableIRIn(); 

  on_servo.write(0);

  off_servo.write(180);

}



void loop()

{

  if (irrecv.decode(&results))

    {

     if(results.value == 0xFFFFFFFF) 

     {

        results.value=Previous;

     }

     switch (results.value){

      case Button_1: Serial.println("on"); on_servo.write(120); delay(1000); on_servo.write(0); break;

      case Button_1_1: Serial.println("on"); on_servo.write(120); delay(1000); on_servo.write(0); break;

      case Button_1_2: Serial.println("on"); on_servo.write(120); delay(1000); on_servo.write(0); break;

      case Button_1_3: Serial.println("on"); on_servo.write(120); delay(1000); on_servo.write(0); break;

      case Button_2: Serial.println("on"); off_servo.write(0); delay(1000); off_servo.write(180); break;

      case Button_2_1: Serial.println("on"); off_servo.write(0); delay(1000); off_servo.write(180); break;

      case Button_2_2: Serial.println("on"); off_servo.write(0); delay(1000); off_servo.write(180); break;

      case Button_2_3: Serial.println("on"); off_servo.write(0); delay(1000); off_servo.write(180); break;

     }

     Serial.println(results.value, HEX);

     irrecv.resume(); 

    }

}
