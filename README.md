# internet-of-things

1.https://wokwi.com/projects/333796636268429907

 2. : https://wokwi.com/projects/333797944251646547
 
3. Arduino RGB LED:https://wokwi.com/projects/333805042897257042

4.tempature & humadity sensor :https://wokwi.com/projects/334347223081943635
INFROMATION
https://arduinogetstarted.com/tutorials/arduino-temperature-humidity-sensor

5.ulaTRA SONIC
:https://wokwi.com/projects/334343126477963859
INFROMATION https://howtomechatronics.com/tutorials/arduino/ultrasonic-sensor-hc-sr04/

6.PIR
https://wokwi.com/projects/334345672871379538
INFROMATION
https://create.arduino.cc/projecthub/biharilifehacker/arduino-with-pir-motion-sensor-fd540a


7.IR:https://wokwi.com/projects/334347798007775826

8.LED blink
https://wokwi.com/projects/334431528065958484

9.led button
https://wokwi.com/projects/334434595516711506
 
 10.led fade
 https://wokwi.com/projects/334437033746367059
 
  11.ultrasonic sensor
  https://wokwi.com/projects/334439407312437842
  
  
  
 12. **  servo motor**
  https://wokwi.com/projects/334976724538229330
  
  13.**  servo motor using potentiometer**
https://wokwi.com/projects/334978058200023635
  
 14. **   button servo motor**
  https://wokwi.com/projects/334980785848189523
  
  15.**  ultrasonic sensor by servo motor**
  https://wokwi.com/projects/334982050944647763
  
  16.**  buzzer**
  https://wokwi.com/projects/335067073514308180
  
 17. **   buzzer with push button**
  https://wokwi.com/projects/335069682709037651
  
  18.**  buzzer with ultrasonic sensor**
  https://wokwi.com/projects/335072835140584019
  
  19.buzzer with different sounds
https://wokwi.com/projects/335066652092662356

20.buzzer with ultrasonic for 20cm
https://wokwi.com/projects/335613396042908243

21.buzzer with led and ultrasonic
https://wokwi.com/projects/335613483142873684

**  22.potentiometer**
https://wokwi.com/projects/335701881854624340

**  23.potentiometer with fade led**
https://wokwi.com/projects/335702970231423572

**lab list program**
 1.https://wokwi.com/projects/338227139367141971 (1. to turn LED on for 1 sec after every 2 sec)

2.https://wokwi.com/projects/338226711455859284 (2. turn on the LED when pushbutton is pressed)

3.https://wokwi.com/projects/338147082096345683 (DHT22 humidity sensor with temperature)

4.https://wokwi.com/projects/335705347315466835 (servomoter with pushbutton)

5.https://wokwi.com/projects/338154081559249491 (DHT22+LCD)


**DHT11:-**
**..................**

    #include <Adafruit_Sensor.h><br>
    #include <DHT.h>;<br>
    #define DHTPIN 13     // what pin we're connected to<br>
    #define DHTTYPE DHT11   // DHT 22  (AM2302)<br>
    DHT dht(DHTPIN, DHTTYPE); //// Initialize DHT sensor for normal 16mhz Arduino<br>
    //Variables<br>
    int chk;<br>
    float hum;  //Stores humidity value<br>
    float temp; //Stores temperature value<br>
    void setup()<br>
    {<br>
      Serial.begin(9600);<br>
      dht.begin();<br>
    }<br>
    void loop()<br>
   {<br>
       delay(2000);<br>
       //Read data and store it to variables hum and temp<br>
       hum = dht.readHumidity();<br>
       temp= dht.readTemperature();<br>
       //Print temp and humidity values to serial monitor<br>
       Serial.print("Humidity: ");<br>
       Serial.print(hum);<br>
       Serial.print(" %, Temp: ");<br>
       Serial.print(temp);<br>
       Serial.println(" Celsius");<br>
       delay(1000); //Delay 2 sec.<br>
   }<br>
   <br>
   **IR SENSOR:-**<br>
  **................**<br>
int ir=D7;<br>
int led=D6;<br>
void setup() {<br>
  // put your setup code here, to run once:<br>
  pinMode(ir,INPUT);<br>
    pinMode(led,OUTPUT);<br>
    Serial.begin(9600);<br>
    <br>
}<br>
<br>
void loop() {<br>
  // put your main code here, to run repeatedly:<br>
  int irvalue=digitalRead(ir);<br>
  if(irvalue==LOW)<br>
  {<br>
    Serial.println("LOW");<br>
    digitalWrite(led,HIGH);<br>
  }<br>
  else<br>
  {<br>
    Serial.println("HIGH");<br>
    digitalWrite(led,LOW);<br>
  }<br>
delay(100);<br>
}<br>
**ultra sonic:-**<br>
**.....................**<br>
const int trigPin = 13; //D7<br>
   const int echoPin = 12; //D6<br>
<br>
   long duration;<br>
   float distanceCm;<br>
   float distanceInch;<br>
<br>
   void setup() {<br>
           Serial.begin(9600); // Starting Serial Terminal<br>
   }<br>
<br>
   void loop() {<br>
      long duration, inches, cm;<br>
      pinMode(trigPin, OUTPUT);<br>
      digitalWrite(trigPin, LOW);<br>
      delayMicroseconds(2);<br>
      digitalWrite(trigPin, HIGH);<br>
      delayMicroseconds(10);<br>
      digitalWrite(trigPin, LOW);<br>
      pinMode(echoPin, INPUT);<br>
      duration = pulseIn(echoPin, HIGH);<br>
      inches = microsecondsToInches(duration);<br>
      cm = microsecondsToCentimeters(duration);<br>
      Serial.print(inches);<br>
      Serial.print("in, ");<br>
      Serial.print(cm);<br>
      Serial.print("cm");<br>
      Serial.println();<br>
      delay(1000);<br>
   }<br>
<br>
   long microsecondsToInches(long microseconds) {<br>
       return microseconds / 74 / 2;<br>
   }<br>
<br>
  long microsecondsToCentimeters(long microseconds) {<br>
    return microseconds / 29 / 2;<br>
   }<br>
**RGB:-**<br>
**................**<br>
 int red = D1;<br>
int green = D6;<br>
int blue = D7;<br>
//GROUND IS CONNECTED TO 3V<br>
void setup() {<br>
pinMode(red, OUTPUT);<br>
pinMode(green, OUTPUT);<br>
pinMode(blue, OUTPUT);<br>
<br>
}<br>
<br>
void loop() {<br>
displayColor(0b100); //RED<br>
delay(1000);<br>
displayColor(0b010); //GREEN<br>
delay(1000);<br>
displayColor(0b001); //BLUE<br>
delay(1000);<br>
displayColor(0b101); //MAGENTA<br>
delay(1000);<br>
displayColor(0b011); //CYAN<br>
delay(1000);<br>
displayColor(0b110); //YELLOW<br>
delay(1000);<br>
displayColor(0b111); //WHITE<br>
delay(1000);<br>
}<br>
<br>
void displayColor(byte color) {<br>
digitalWrite(red, !bitRead(color, 2));<br>
digitalWrite(green, !bitRead(color, 1));<br>
digitalWrite(blue, !bitRead(color, 0));<br>
}<br>
**LDR:-**<br>
**...................**<br>
const int ldrPin=A0;<br>
<br>
void setup() {<br>
  // put your setup code here, to run once:<br>
  Serial.begin(9600);<br>
  pinMode(ldrPin,INPUT);<br>
<br>
}<br>
<br>
void loop() {<br>
  // put your main code here, to run repeatedly:<br>
  int rawData=analogRead(ldrPin);<br>
  Serial.println(rawData);<br>
  delay(1000);<br>
}<br>
LDR WITH LED:-<br>
........................................<br>
int ldr=A0;//Set A0(Analog Input) for LDR.<br>
 int value=0;<br>
 int led=D4;<br>
 void setup() {<br>
 Serial.begin(9600);<br>
 pinMode(led,OUTPUT);<br>
 }<br>
<br>
 void loop() {<br>
 value=analogRead(ldr);//Reads the Value of LDR(light).<br>
 Serial.println("LDR value is :");//Prints the value of LDR to Serial Monitor.<br>
 Serial.println(value);<br>
 if(value<50)<br>
   {<br>
     digitalWrite(led,HIGH);//Makes the LED glow in Dark.<br>
   }<br>
   else<br>
   {<br>
     digitalWrite(led,LOW);//Turns the LED OFF in Light.<br>
   }<br>
   delay(1000);<br>
 }<br>
![image](https://user-images.githubusercontent.com/104187589/185892277-3ebd6063-a94a-41a0-b638-826a5b650690.png)<br>
 
 
**flood monitoring system link:-**
https://theiotprojects.com/iot-based-flood-monitoring-system-using-nodemcu-thingspeak/


