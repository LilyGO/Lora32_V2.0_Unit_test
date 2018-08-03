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

---

### Unit 2 Bluetooth

Phone pairing to connect to Bluetooth

```c
void setup() {
  Serial.begin(115200);
  SerialBT.begin("ESP32test"); //Bluetooth device name
  Serial.println("The device started, now you can pair it with bluetooth!");
  Serial.println("My name is ESP32test");
}
```
ESP32 Bluetooth name is set by SerialBT.begin()

---

### Uint 3 wifi

#### wifi_scan
Wifi scan serial port information display can connect wifi name and signal strength

```c
 Serial.begin(115200);

    // Set WiFi to station mode and disconnect from an AP if it was previously connected
    WiFi.mode(WIFI_STA);
    WiFi.disconnect();
    delay(100);

    Serial.println("Setup done")
```

#### wifi_web_sever

By connecting to WiFi, you can generate a web page.

```c
const char* ssid = "TP-LINK-";//Please input your wifi ID
const char* password = "123456";//Please input your wifi password

//Log in with a browser to generate a mac address:
//example:192.168.0.108
digitalWrite(led, 1);
server.send(200, "text/plain", "hello from esp32!");
digitalWrite(led, 0);
```
Log in to 192.168.0.x,The screen will display:"hello from esp32!"

---

### Unit 4 SD card

Read the name of the SD card storage information according to the serial port information.

```C
  Serial.begin(115200);
  pinMode(LED_BUILTIN, OUTPUT);
  Serial.print("Initializing SD card...");
  /* initialize SD library with SPI pins */
 if (!SD.begin(13,15,2,14)) {            //T1:13,15,2,14  T2: 23,5,19,18 M5：4,23,19,18 uint8_t csPin, int8_t mosi, int8_t miso, int8_t sck
    Serial.println("initialization failed!");
    return;
  }
  Serial.println("initialization done.");
```
Please note that the baud rate is consistent

---

### Unit 5 Lora && OLED

Lora_send send data Lora_receive
 
![images](https://github.com/LilyGO/TTGO-LORA32-V2.0/blob/master/images/image4.jpg)
