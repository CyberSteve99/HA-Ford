# HA-Ford
HomeAssistant and FordConnect Query Home Assistant Integration 2026 (EV/PHEV/Petrol/Diesel)

I have a Campervan built on a Ford Transit Base and wanted to monitor the data that Ford collects and produce some pretty graphs using Grafana.

As a user of HomeAssistant and Grafana I wanted to monitor systems in my campervan and record and display various metrics from various sources.

The Ford Sync system in my van talks back to Ford and monitors various metrics which I guess is where the Ford Sync App gets its information from. There is a HomeAssistant integration which enables us to pull in that data and expose it in HomeAssistant and the metrics are then held within the HomeAssistant database (I use MariaDB as the DB backend for HomeAssistant) and that data can then be used in tools such as Grafana.

I’ll not cover using HomeAssistant or Grafana in this blog as that can be found elsewhere on the internet. I’ll cover some of what I used and did to produce some graphs like this in Grafana.

 <img width="452" height="229" alt="image" src="https://github.com/user-attachments/assets/54ff7ee4-44fd-4be0-8ffa-3db03490dfa2" />



## The FordConnect Query Home Assistant Integration 2026 (EV/PHEV/Petrol/Diesel)

See https://github.com/marq24/ha-fordconnect-query for details to get the integration working in HomeAssistant. It’s quite complex and the steps need to be followed closely but once done the sensors are exposed in HomeAssistant.

 <img width="452" height="250" alt="image" src="https://github.com/user-attachments/assets/02cf22e3-f7cb-46b5-959a-c2ba61d3bba6" />


Ford Sync data is now available in HomeAssistant. Clicking any sensor shows the graphs for that sensor’s values.

Next step is to Produce Grafana graphs. I have created a file that can be imported into Grafana. It's in the grafana directory.

