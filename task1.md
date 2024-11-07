# interface
// C++ code
//Maya sarary 1210607 - Masa Ghith 1211458 
//Reem Samhan 1210221 - Mohammad Abushama 1200270
#define green 8
#define yellow 9
#define red 10

#define trig 2
#define echo 3
void setup(){
	pinMode(green,OUTPUT);
  	pinMode(yellow,OUTPUT);
 	pinMode(red,OUTPUT);
  	pinMode(echo,INPUT);
  	pinMode(trig,OUTPUT);
}

void loop(){
  long duration, cm;
  
  digitalWrite(trig,LOW);
  delayMicroseconds(2);
  digitalWrite(trig,HIGH);
  delayMicroseconds(10);
  digitalWrite(trig,LOW);
  
  duration = pulseIn(echo,HIGH);
  cm = duration * 0.34 / 2 ;
  
  long distance = map(analogRead(A5),0,1023,1,12) ;
  
    if(cm>20*distance){
    digitalWrite(green,HIGH);
  	digitalWrite(yellow,LOW);
    digitalWrite(red,LOW);
  }
  else if(cm<= 20*distance && cm>=10*distance){
    digitalWrite(green,LOW);
  	digitalWrite(yellow,HIGH);
    digitalWrite(red,LOW);
  }
  else {
   digitalWrite(green,LOW);
  	digitalWrite(yellow,LOW);
    digitalWrite(red,HIGH);
  }

  
}
