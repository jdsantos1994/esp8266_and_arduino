* ESP8266 mqtt node

#### Server ####
- mqtt broker : mosquitto
- db : influxdb
- web : grafana, node-red
- collect : mqtt2graphite
- alert : mqttwarn 


![1](https://raw.githubusercontent.com/chaeplin/esp8266_and_arduino/master/_01-door-alarm/pics/01.png)
![2](https://raw.githubusercontent.com/chaeplin/esp8266_and_arduino/master/_06-power-meter/pics/1.jpg)
![3](https://raw.githubusercontent.com/chaeplin/esp8266_and_arduino/master/_02-mqtt-sw/pics/4.jpg)
![4](https://raw.githubusercontent.com/chaeplin/esp8266_and_arduino/master/_03-hx711-scale/pics/1.jpg)
![5](https://raw.githubusercontent.com/chaeplin/esp8266_and_arduino/master/_04-mqtt-lcd-dust-sensor/pics/3.jpg)

#### _01-door-alarm ####
- esp-12 +(gpio) pro mini
- active buzzer, magnetic door sw, capacitor, battery
- pub door status, using pro mini as external interrupt


#### _02-mqtt-sw ####
- esp-12
- power(5v + 3.3V), fuse(10A + 73°C thermal), 1CH relay, SW(top + lamp), PIR, DS18B20(in + out), DHT22
- on/off lamp using mqtt, pub temp(inside of box + outside)/humidity/pir


#### _03-hx711-scale ####
- esp-12 +(i2c) pro mini
- hx711, load cell
- pub measured weight of pet


#### _04-mqtt-lcd-dust-sensor ####
- esp-01 +(i2c) nano
- lcd(i2c), rtc(i2c), level convertor, Sharp dust sensor
- display clock, temp/humidity(mqtt sub), dust


#### _05-two-ds18b20 ####
- esp-12
- 2 x DS18B20, battery
- pub temp(inside + outside)


#### _06-power-meter ####
- esp-12
- CT sensor, line tracker
- pub power usage
