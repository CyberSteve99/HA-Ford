# HA-Ford
HomeAssistant and FordConnect Query Home Assistant Integration 2026 (EV/PHEV/Petrol/Diesel)

I have a Campervan built on a Ford Transit Base and wanted to monitor the data that Ford collects and produce some pretty graphs using Grafana.

As a user of HomeAssistant and Grafana I wanted to monitor systems in my campervan and record and display various metrics from various sources.

The Ford Sync system in my van talks back to Ford and monitors various metrics which I guess is where the Ford Sync App gets its information from. There is a HomeAssistant integration which enables us to pull in that data and expose it in HomeAssistant and the metrics are then held within the HomeAssistant database (I use MariaDB as the DB backend for HomeAssistant) and that data can then be used in tools such as Grafana.

I’ll not cover using HomeAssistant or Grafana in this blog as that can be found elsewhere on the internet. I’ll cover some of what I used and did to produce some graphs like this in Grafana.

<img width="1364" height="719" alt="image" src="https://github.com/user-attachments/assets/03a991f6-9117-4d05-bbbe-0febf4bc886c" />


## The FordConnect Query Home Assistant Integration 2026 (EV/PHEV/Petrol/Diesel)

See https://github.com/marq24/ha-fordconnect-query for details to get the integration working in HomeAssistant. It’s quite complex and the steps need to be followed closely but once done the sensors are exposed in HomeAssistant.

<img width="1301" height="619" alt="image" src="https://github.com/user-attachments/assets/af8661d6-d8eb-4f19-ab1b-0a66eaa11be1" />

Ford Sync data is now available in HomeAssistant. Clicking any sensor shows the graphs for that sensor’s values.

Next step is to Produce Grafana graphs. I have created a file that can be imported into Grafana. It's in the grafana directory.

## Monitoring Victron Devices

To monitor my Victron Devices in HomeAssistant and graph in Grafana I use the HomeAssistant Victron BLE integration (https://www.home-assistant.io/integrations/victron_ble/)

<img width="1366" height="804" alt="image" src="https://github.com/user-attachments/assets/dab7b455-4c62-4524-9355-d81c17919894" />

<img width="1136" height="678" alt="image" src="https://github.com/user-attachments/assets/764b41e4-ec52-43a3-8580-29305ade4330" />

## My Setup

I have a Raspberry Pi running HomeAssistant and Grafana at home and this runs the HA Ford integration.

I have another Raspberry Pi in the van along with an ESP32 configured with ESPHome acting as a Bluetooth Low Energy (BLE) Proxy with the Victron BLE HomeAssistant integration as this collects the Victron devices information and needs to be within Bluetooth range. The ESP32 is also configured to collect data from my Fogstar Drift battery BMS. The Raspberry Pi and ESP32 in the van use the WiFi in the van which uses an Avtex router and is permanently powered. I use Tailscale as a VPN so that I can connect to the Raspberry Pi in the van from anywhere and query the HomeAssistant database from Home.
