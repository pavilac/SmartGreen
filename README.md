# SmartGreen - Arduino Project
ESP8266 soil humidity meter that sends alerts through Telegram

Materials list:
- ESP8266 12E
- Capacitive soil humidity sensor v1.2 connected to A0
- 0.96" Oled display (Optional) connected to I2C port

SmartGreen is capable of:
- Create an AP for WiFi configuration. Once configured it works on station mode only
- Send alert messages to a telegram group when soil humidity is under a defined threshold
- Configure by telegram messages:
   - Actual soil humidity
   - Dry and humid sensor limits (Depends on soil)
   - Notification humidity threshold level
- Show device moods on display

## Introduction
This code creates an interface between a Telegram Bot in a group and a Arduino (Any), providing total control over it. Following Libraries were used:

1. [WiFiManager](https://github.com/tzapu/WiFiManager): to create AP and manage WIFI connection
2. [CTBot](https://github.com/shurillu/CTBot): To interface with telegram group
3. [Adafruit_SSD1306](https://github.com/adafruit/Adafruit_SSD1306): To manange display

## Telegram BOT
First, it is necessary to create a Telegram Bot, once you do it you are given an Access Token, Name and Username that must be changed in ESP. To create your Telegram Bot, talk to BotFather and follow a few simple steps described [here](https://core.telegram.org/bots#botfather).

Check last Telegram API documentation at: https://core.telegram.org/bots/api.

The code is made so more than one user can control and receive alerts from the bot, thus it is also neccesary to create a group and add the bot to the group, allowing it to read the messages.

### Installation
The downloaded libraries can be included as a new library into the Arduino IDE selecting the menu:
```
Sketch / include Library / Add .Zip library
```
## Commands
Next commands can be send to Telegram bot:
- **/start** gives a welcome message
- **/humedad** returns the actual soil humidity
- **/seco** configures the dry sensor level
- **/humedo** configures the humid sensor level
- **/nivel#** changes the humidity threshold level
