//SMOKE DETECTOR
// library for the lcd screen
#include "LiquidCrystal.h"
LiquidCrystal lcd(8, 7, 6, 5, 4, 3); // available pinholes for the lcd scren

int smoke = 0; // defining base value for smoke to trigger sensors in future condiion
int buzz = 9;  // buzzer pinhole

void setup() // setting basic inputs and pinholes to be detected
{
    pinMode(13, OUTPUT); // led pinholes to the arduino(red)
    pinMode(12, INPUT);
    pinMode(10, OUTPUT);
    pinMode(11, OUTPUT);

    pinMode(A0, INPUT); // input to read the gas sensor
    Serial.begin(9600);
    lcd.begin(16, 2);

    lcd.setCursor(0, 0);
    lcd.print("   Smoke Sensor  ");

    pinMode(buzz, OUTPUT); // sets the piezo as an output for sound
}

void loop()
{
    int status = digitalRead(12);      // LED lights when switch is flipped
    if (status == HIGH && smoke < 150) // green LED condition
    {
        digitalWrite(10, HIGH); // green lights
        digitalWrite(13, LOW);  // red off
        digitalWrite(11, LOW);  // yellow off
        noTone(buzz);           // buzzer doesnt buzz when green
    }
    else if (status == HIGH && smoke > 150 && smoke < 275) // yellow led condition(have to add 3 or the red LED wont light up)
    {
        digitalWrite(11, HIGH); // yellow lights
        digitalWrite(13, LOW);  // red off
        digitalWrite(10, LOW);  // green off
        tone(buzz, 100);        // buzzer turns on at this tone if yellow threshold is met
        delay(200);
        noTone(buzz);
    }
    else if (status == HIGH && smoke > 275) // red led condition
    {
        digitalWrite(13, HIGH); // red lights
        digitalWrite(11, LOW);  // yellow off
        digitalWrite(10, LOW);  // green off
        tone(buzz, 333);        // buzzer turns on at this louder tone if red threshold is met
        delay(100);
        noTone(buzz);
    }
    else
    { // turns all the leds off when the switch is off
        digitalWrite(10, LOW);
        digitalWrite(11, LOW);
        digitalWrite(13, LOW);
    }

    smoke = analogRead(A0); // smoke sensro connected to this analog pinhole (A0) so must be read here
    Serial.println(smoke);

    // conditions for the lcd screen to change if smoke is detected or not
    if (smoke > 150)
    {
        lcd.setCursor(0, 1);
        lcd.print("Smoke Detected");
    }
    else
    {
        lcd.setCursor(0, 1);
        lcd.print("Smoke Not Detect");
    }

    delay(13); // Delay a little bit to run better
}
