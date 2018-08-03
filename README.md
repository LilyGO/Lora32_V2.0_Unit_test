## Lora32_V2.0_Unit_test

### Unit 1 Blink

LED can change Blink frequency by changing delay time

```C
digitalWrite(LED_BUILTIN, HIGH);   // turn the LED on (HIGH is the voltage level)
delay(1000);                       // wait for a second
Serial.println("blink on");
digitalWrite(LED_BUILTIN, LOW);    // turn the LED off by making the voltage LOW
delay(1000);                       // wait for a second
```

Flash every second

