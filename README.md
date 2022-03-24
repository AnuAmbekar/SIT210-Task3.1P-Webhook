# SIT210-Task3.1P-Webhook

// This #include statement was automatically added by the Particle IDE.
#include <Adafruit_DHT.h>

//#include "Adafruit_DHT.h"

#define DHTTYPE DHT11
#define DHTPIN A0


DHT dht(DHTPIN, DHTTYPE);


void setup() {
    
  dht.begin();
  
}

void loop() {

  float temp = dht.getTempCelcius();
  Particle.publish("temp", String(temp), PRIVATE);
  delay(3000);

}
