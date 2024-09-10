// C++ code
//TEMPERATURE DETECTOR
// library for the lcd screen

#include <LiquidCrystal_I2C.h>

LiquidCrystal_I2C lcd(32, 16, 2);
int sensorPin = 0;
// start the lcd screen for ARDUINO 1
void setup()
{
    Serial.begin(9600);
    lcd.init();
    lcd.backlight();
}

void loop()
{
    // read the temp sensor connection in the analog pin (A0)
    int reading = analogRead(sensorPin); // get input from and readings from temp sensor

    float voltage = reading * 4.68;
    voltage /= 1024.0;

    // show temperature

    float temperatureC = (voltage - 0.5) * 100;
    Serial.print(temperatureC);
    Serial.println(" degrees C");

    lcd.setCursor(0, 0); // location of below printed statement on the screen
    lcd.print("Temperature Value ");
    lcd.setCursor(0, 1); // location of below printed statement on the screen
    lcd.print(" degrees C");
    lcd.setCursor(11, 1);    // location of below printed statement on the screen
    lcd.print(temperatureC); // display temp value

    delay(100);
}

// C++ code
// library for the lcd screen
#include "LiquidCrystal.h"
LiquidCrystal lcd(8, 7, 6, 5, 4, 3); // pin holes we can use on arduino
int sensorPin = 0;

// start the lcd screen for ARDUINO 2
void setup()
{
    Serial.begin(9600);
    lcd.begin(16, 2);
}

void loop()
{
    // read the temp sensor connection in the analog pin (A0)
    int reading = analogRead(sensorPin); // get input from and readings from temp sensor

    // celcius equation???(not sure if supposed to use this or the direct reading from the temp sensor)
    // float voltage = reading * 4.68;
    // voltage /= 1024.0;

    // show temperature

    // float temperatureC = (voltage - 0.5) * 100;
    Serial.print(reading);
    Serial.println(" degrees C");

    lcd.setCursor(0, 0); // location of below printed statement on the screen
    lcd.print("Temperature Value ");
    lcd.setCursor(0, 1); // location of below printed statement on the screen
    lcd.print(" degrees C");
    lcd.setCursor(11, 1); // location of below printed statement on the screen
    lcd.print(reading);   // display temp value

    delay(100);
}
