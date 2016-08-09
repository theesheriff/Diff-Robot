# Diff-Robot


/*
define components: 
Enabler pins(2),for motors 1 and 2
Control pins(4), 2 for each motor
pushButtons(2)-one for speed the other for direction.


*/

#define En1 10
#define I1 9
#define I2 8

#define En2 11
#define I3 12
#define  I4 13


void setup() {
  // put your setup code here, to run once:

  //Enabler pins and Control pins all OUTPUTS.
    pinMode(En1, OUTPUT);
    pinMode(I1, OUTPUT);
    pinMode(I2, OUTPUT);

    pinMode(En2, OUTPUT);
    pinMode(I3, OUTPUT);
    pinMode(I4, OUTPUT);
  
}

void loop() {
  // put your main code here, to run repeatedly:
         forward();
            delay(10);
         right();
            delay(10);
         left();
          delay(10);
         backwards();
         
}

  void forward(){
        analogWrite(En1, 255);
        analogWrite(En2, 255);

        digitalWrite(I1, HIGH);
        digitalWrite(I2, LOW);
        
        digitalWrite(I3, HIGH);
        digitalWrite(I4, LOW);

        delay(1000);
        }

    void backwards(){
       analogWrite(En1, 255);
       analogWrite(En2, 255);
      
       digitalWrite(I1, LOW);
       digitalWrite(I2, HIGH);
      
       digitalWrite(I3, LOW);
       digitalWrite(I4, HIGH);

       delay(1000);
       }

    void right(){
        analogWrite(En1, 255);
        analogWrite(En2, 95);
      
        digitalWrite(I1, HIGH);
        digitalWrite(I2, LOW);
      
        digitalWrite(I3, HIGH);
        digitalWrite(I4, LOW);

        delay(1000);
      }

    void left(){
      analogWrite(En1, 95);
      analogWrite(En2, 255);

      digitalWrite(I1, HIGH);
      digitalWrite(I2, LOW);

      digitalWrite(I3, HIGH);
      digitalWrite(I4, LOW);

      delay(1000);
    }

    //incorporating pushButtons
   /* 
    const int pushSpeed=5; //assign pin 5 to push button for controlling speed
    const int pushDir=6; //assign pin 6 to push button for controlling direction

    int valSpeed=0; //store value of speed state(high or low)
    int oldSpeed=0; //store previous value of speed state
    int state=0; //state of the bot,On or Off
    
    int valDir=0; //store value of direction state(high or low)
    int oldDir=0; //store old value of direction state

    int speed=130; //store speed value

    unsigned long startSpeedTime=0;

    //setup:
    pinMode(pushSpeed, INPUT);
    pinMode(pushDir, INPUT);

    //loop;
    valSpeed=digitalRead(pushSpeed);
    //check if there was a transition:
    if((valSpeed==HIGH)&&(oldSpeed==LOW))
    {
      state=1-state; //change bot state on/off accordingly

      startSpeedTime=millis(); //check when the speed button was last pressed
      delay(10);
    }

    //check if the button is being long pressed:
    if((valSpeed==HIGH)&&(oldSpeed==HIGH))
    {
      //if press is > 500ms:
      if((state==1)&&(millis()-startSpeedTime)>500)
      {
        speed++;//increase speed
        delay(10);

        if (speed>255)
        {
          delay(10000);
          speed--;
          delay(10);
        }
      }
    }

    oldSpeed=valSpeed;

    if(state==1)
    {
      analogWrite(En1, speed);
      analogWrite(En2, speed);
    }
      else{
        analogWrite(En1, 0);
        analogWrite(En2, 0);
      }
//incomplete, the pushDir button hasn't been incorporated yet.
    */

    
    
