# Rightech IoT with MQTT

## Quick start

### 1. Create MQTT model

![mqtt-create-model](https://github.com/user-attachments/assets/392134b2-e177-4e9f-97ca-ed5874fb2454)



### 2. Create object

![mqtt-create-object](https://github.com/user-attachments/assets/666e3420-72b3-4b96-8acd-1629da7f7454)


### Настройки аутентификации MQTT

![mqtt-issue-cert](https://github.com/user-attachments/assets/0db1e5c9-1790-4142-8987-eed7b44e7b91)

### Настройка Wi-Fi и MQTT в PlatformIO (IoT)
![mqtt-esp32-platformio-vscode](https://github.com/user-attachments/assets/2f5e65f0-af5f-439b-b801-6907c94b09e6)



### 3. Send some payloads

![mqtt-send-data](https://github.com/user-attachments/assets/21b06ac3-fce0-4b41-b885-97f8ea105ce3)


For example with `mosquitto_pub` client from [Eclipse Mosquitto](https://mosquitto.org/download/) project.

```console
$ mosquitto_pub -d -h dev.rightech.io -i <ric-mqtt-client-id> -t base/state/temperature -m 23
$ mosquitto_pub -d -h dev.rightech.io -i <ric-mqtt-client-id> -t base/state/temperature -m 24
```

Or any other MQTT client tool like:
 - [MQTT.fx](https://mqttfx.jensd.de/)
 - [MQTT Explorer](https://mqtt-explorer.com/)


## Examples

### 101  Hello MQTT

Connect to Rightech IoT and publish to some topics.  
  (Also listen to some commands)

> **WARNING**: Using only MQTT `clientId` is very basic and examplish method of device identification/authentication.  
We recommend using X.509 client certificates, or at least MQTT `username`/`password` pair.

| Board          | Framework   |  Example
| -------------- | ----------- | ----------
| Raspberry Pi   | Node.js     | [101-hello.js](./nodejs/101-hello.js)
| NodeMCU        | Arduino     | [101-hello.ino](./arduino/101-hello.ino)


### 102  Connect DHT11

| Board          | Framework   |  Example
| -------------- | ----------- | ----------
| Raspberry Pi   | Node.js     | [102-dht11.js](./nodejs/102-dht11.js)
| NodeMCU        | Arduino     | [102-dht11.ino](./arduino/102-dht11.ino)


### 103  Publish and subscribe JSON

| Board          | Framework   |  Example
| -------------- | ----------- | ----------
| Raspberry Pi   | Node.js     | [103-json.js](./nodejs/103-json.js)
| NodeMCU        | Arduino     | [103-json.ino](./arduino/103-json.ino)

### 104  TLS

| Board          | Framework   |  Example
| -------------- | ----------- | ----------
| Raspberry Pi   | Node.js     | [104-tls.js](./nodejs/104-tls.js)
| NodeMCU        | Arduino     | [104-tls.ino](./arduino/104-tls.ino)


### 201  RTOS
| Board          | Framework   |  Example
| -------------- | ----------- | ----------
| ESP32          | ESP-IDF     | [esp-idf](./esp-idf#readme)

## Connect

| Project       | With example model     |  Config
| ------------- | ---------------------- | ----------
| [ESPHome](https://esphome.io/)   | - | [config.yaml](./esphome/config.yaml)
| [OpenMQTTGateway](https://github.com/1technophile/OpenMQTTGateway)   | [model.json](../.ric-models/mqtt-omg.ric-model.json)  | -
| [OctoPrint](https://octoprint.org/)                                  | [model.json](./octoprint/model.json)   | [config.yaml](./octoprint/config.yaml)
| [zigbee2mqtt](https://github.com/Koenkk/zigbee2mqtt)                 | [model.json](./zigbee2mqtt/model.json) | [configuration.yaml](./zigbee2mqtt/configuration.yaml)
| [LoRa Server](https://github.com/brocaar/loraserver)                 | [model.json](../.ric-models/mqtt-loraserver-td11.ric-model.json)  | -
