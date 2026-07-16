# Trafic Light Using Arduino For JEAI Class

## Agenda
1. Digital OUTPUT 

Branch - `v1`

![alt text](images/image.png)
```cpp
#include <Arduino.h>

#define DELAY 3000
int red_led_pin = 6;
int yellow_led_pin = 5;
int green_led_pin = 4;
void turn_on(int);
void turn_off(int);
void activate(int);

int pins[3] = {red_led_pin,yellow_led_pin,green_led_pin};
void setup() {
    Serial.begin(9600);
    for(int i = 0; i < sizeof(pins)/sizeof(int) ; ++i ) {
        pinMode(pins[i], OUTPUT);
    }
}


void loop() {
    for(int i = 0; i < sizeof(pins)/sizeof(int) ; ++i ) {
        activate(pins[i]);
    }
}
void turn_on(int pin){
    Serial.print(F("TURNING ON PIN "));
    Serial.println(pin);
    digitalWrite(pin,HIGH);
}
void turn_off(int pin){
    Serial.print(F("TURNING OFF PIN "));
    Serial.println(pin);
    digitalWrite(pin, LOW);
}
void activate(int pin){
    int delay_ms = DELAY;
    turn_on(pin);
    delay(delay_ms);
    turn_off(pin);
}

```

Branch - `v2`
![alt text](images/image-1.png)

Branch - `v3`
![alt text](images/image-2.png)

Branch - `V4` 
![alt text](images/image-3.png)

