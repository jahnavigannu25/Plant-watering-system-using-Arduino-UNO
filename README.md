# Plant-watering-system-using-Arduino-UNO

This project is an automatic watering system using an Arduino. The system uses a soil moisture sensor to detect the moisture level of the soil and controls a relay to turn on or off a water pump accordingly.

## Components
- Arduino (any model)
- Soil Moisture Sensor
- Relay Module
- Water Pump
- Connecting Wires
- Power Source

## Circuit Diagram
Connect the components as follows:

- **Soil Moisture Sensor**: 
  - VCC to Arduino 5V
  - GND to Arduino GND
  - Signal to Arduino pin 6

- **Relay Module**: 
  - VCC to Arduino 5V
  - GND to Arduino GND
  - IN to Arduino pin 3
  - Connect the relay output to the water pump

## Code
Upload the following code to your Arduino:

```cpp
int water; // random variable 

void setup() {
  pinMode(3, OUTPUT); // output pin for relay board, this will send a signal to the relay
  pinMode(6, INPUT); // input pin coming from soil sensor
}

void loop() { 
  water = digitalRead(6); // reading the incoming signal from the soil sensor
  if (water == HIGH) { // if water level is full, then cut the relay 
    digitalWrite(3, LOW); // LOW is to cut the relay
  } else {
    digitalWrite(3, HIGH); // HIGH to continue providing signal and water supply
  }
  delay(400); 
}
