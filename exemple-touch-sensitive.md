# Exemple Touch sensitive

Faire le montage avec simplement un fil en l’air dont l'autre extrémité est reliée à la broche GPIO4.  Nous le serrerons avec les doigts pour faire allumer la LED bleue présente sur l’ESP32 (GPIO2) au-delà d’un seuil (threshold) fixé à l’avance.

```arduino
// set pin numbers
const int touchPin = 4;  // GPIO4
const int ledPin = 2;  // GPIO2 : Blue LED of the NodeMCU

// change with your threshold value
const int threshold = 25;
// variable for storing the touch pin value 
int touchValue;

void setup(){
  Serial.begin(115200);
  delay(1000); // give me time to bring up serial monitor
  // initialize the LED pin as an output:
  pinMode (ledPin, OUTPUT);
}
void loop(){
  // read the state of the pushbutton value:
  touchValue = touchRead(touchPin);
  Serial.print(touchValue);
  // check if the touchValue is below the threshold
  // if it is, set ledPin to HIGH
  if(touchValue < threshold){
    // turn LED on
    digitalWrite(ledPin, HIGH);
    Serial.println(" - LED on");
  }
  else{
    // turn LED off
    digitalWrite(ledPin, LOW);
    Serial.println(" - LED off");
  }
  delay(500);
}
```
