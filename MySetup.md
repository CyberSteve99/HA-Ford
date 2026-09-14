My campervan is a Bailey Endeavour B62

I have an Avtex WiFI solution which I permanently power using an EcoFlow Delta 2

In addition I have a Raspberry Pi4b with NVRAM Solid State storage attached and also powered permanently by the Delta 2.

I also use an ESP32 as an ESPHome Bluetooth Proxy. https://esphome.io/components/bluetooth_proxy/

I run HomeAssistant in a Docker container on the Raspberry Pi4.

I have an ANCEL BM200 Bluetooth Battery Monitor to monitor the Starter Battery via the ESP32.
See https://www.amazon.co.uk/dp/B0DTDWZQJQ?ref_=ppx_hzsearch_conn_dt_b_fed_asin_title_6&th=1

I use Grafana running on a Raspberry Pi4b on my home network to query the HomeAssistant Database on the Pi4b in the campervan over the internet. 
I use Tailscale (https://tailscale.com/) to connect my home network to the Pi4b in the campervan.

