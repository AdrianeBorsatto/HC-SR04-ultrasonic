# HC-SR04-ultrasonic
Ultrasonic HC SR04 + arduino 

O Sensor Ultrassônico HC-SR04 é um componente muito comum em projetos com Arduino, e permite que você faça leituras de distâncias entre 2 cm e 4 metros, com precisão de 3 mm



código sketch para arduino


const int trigPin = 9;
const int echoPin = 10;

float  duration, distance;

void setup() {
  pinMode(trigPin, OUTPUT);
  pinMode(echoPin,  INPUT);
  Serial.begin(9600);
}

void loop() {
  digitalWrite(trigPin,  LOW);
  delayMicroseconds(2);
  digitalWrite(trigPin, HIGH);
  delayMicroseconds(10);
  digitalWrite(trigPin, LOW);

  duration = pulseIn(echoPin, HIGH);
  distance  = (duration*.0343)/2;
  Serial.print("Distance: ");
  Serial.println(distance);
  delay(100);

}
