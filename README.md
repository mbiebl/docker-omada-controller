mbiebl/omada-controller
=========================

docker image based off of ubuntu:18.04 for [TP-Link Omada Controller](https://www.tp-link.com/en/products/details/EAP-Controller.html) to control [TP-Link Omada EAP Series Wireless Access Points](https://www.tp-link.com/en/omada/)

## Tags
  * `latest`, `3.2` - Omada Controller 3.2.x (currently 3.2.6)

## Example usage
To run this Docker image and keep persistent data in named volumes:
```
docker run -d \
  --name omada-controller \
  --restart unless-stopped \
  -e TZ=Europe/Berlin \
  -p 8088:8088 \
  -p 8043:8043 \
  -p 27001:27001/udp \
  -p 27002:27002 \
  -p 29810:29180/udp \
  -p 29811:29811 \
  -p 29812:29812 \
  -p 29813:29813 \
  -v omada-data:/opt/tplink/EAPController/data \
  -v omada-work:/opt/tplink/EAPController/work \
  -v omada-logs:/opt/tplink/EAPController/logs \
  mbiebl/omada-controller
```
