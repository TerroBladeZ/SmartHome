
# Home Assistant Configuration
I run HassIO under Docker using Intel® NUC Kit NUC5i5RYK with Ubuntu 18.04.1 LTS, 16GB RAM and 250GB SSD.
I regularly update my configuration files. If you like anything here, Be sure to 🌟 my repo!!!!

##### Install HassIO with Docker on ubuntu with just 2 command lines. Thanks to  HASSCASTS.

1. sudo apt-get install curl
2. curl -sL goo.gl/goR2HT | bash -


## Devices

### Hub
| Device  | Quantity | Connection | Home Assistant | Notes |
| ------------- | :---: | ------------- | ------------- | ------------- |
| [SmartThings](https://amzn.to/2IpNA3G) | 1 | Ethernet | [SmartThings](https://github.com/stjohnjohnson/smartthings-mqtt-bridge) | Used to bridge all Zigbee smart switches to HA |
| [Lutron Caseta](https://amzn.to/2wMUjis) | 1 | Ethernet | [Lutron](https://www.home-assistant.io/components/lutron/) | Used to connect Lutron Casetta switches |

Relevant hub configurations can be found within [smartthings.yaml](https://github.com/TerroBladeZ/SmartHome/blob/master/packages/smartthings.yaml)

## Climate

| Device  | Quantity | Connection | Home Assistant | Notes |
| ------------- | :---: | ------------- | ------------- | ------------- |
| [Ecobee 4](https://amzn.to/2wv7YHx) | 1 | Wi-Fi | [ecobee](https://www.home-assistant.io/components/ecobee/) | Used as primary thermostat |
| [Ecobee Room Sensor](https://amzn.to/2L9cORm) | 4 | Ecobee4 | [Ecobee Binary Sensor](https://www.home-assistant.io/components/binary_sensor.ecobee/) | Provides room temperature and room occupancy.|

 Ecobee room sensors are used as occupancy sensors with the help of automations to trigger security alarm

## Switch

| Device  | Quantity | Connection| Home Assistant | Notes |
| ------------- | :---: | ------------- | ------------- | ------------- |
| [Lutron Casseta](https://amzn.to/2PGqvtk) | 7 | HUB | [Lutron](https://www.home-assistant.io/components/lutron_caseta/) | Switches to basement and living room lights. |
| [Leviton Decora](https://amzn.to/2MYODc3) | 7 | SmartThings | [Leviton ](https://www.home-assistant.io/components/light.decora/) | Switches to kitchen and bed room lights .|

This switches are all around my house connected via their respective hubs to Smartthings and a bridge to HassIO thru Smartthings Addon.

## Security

| Device  | Quantity | Connection| Home Assistant | Notes |
| ------------- | :---: | ------------- | ------------- | ------------- |
| [NodeMCU Development Boards](http://amzn.to/2ou0NON) | 1 | Wi-Fi/MQTT | [ESPEasy](https://bit.ly/2uswsjt) | Acts as a HUB to wired door sensors |
| [Aura Home Monitoring Motion Alarm](https://amzn.to/2sLX8v6) | 5 | SmartThings | [Ecobee ](https://www.home-assistant.io/components/binary_sensor.ecobee/) | Provides room occupancy.|

<tr><td align="center"><a href="https://www.amazon.com/gp/product/B010O1G1ES/ref=as_li_ss_il?ie=UTF8&psc=1&linkCode=li1&tag=vmw0a-20&linkId=8f30ebb6868e9060be331dd297b75119" target="_blank"><img border="0" src="https://ws-na.amazon-adsystem.com/widgets/q?_encoding=UTF8&ASIN=B010O1G1ES&Format=_SL110_&ID=AsinImage&MarketPlace=US&ServiceVersion=20070822&WS=1&tag=vmw0a-20" ></a><img src="https://ir-na.amazon-adsystem.com/e/ir?t=vmw0a-20&l=li1&o=1&a=B010O1G1ES" width="1" height="1" border="0" alt="" style="border:none !important; margin:0px !important;" />
</td><td align="center"><a href="https://www.amazon.com/dp/B0765HSPB6/ref=as_li_ss_il?_encoding=UTF8&th=1&linkCode=li2&tag=vmw0a-20&linkId=f12d53d66cfe46b18710d985a9f4d883" target="_blank"><img border="0" src="https://ws-na.amazon-adsystem.com/widgets/q?_encoding=UTF8&ASIN=B0765HSPB6&Format=_SL160_&ID=AsinImage&MarketPlace=US&ServiceVersion=20070822&WS=1&tag=vmw0a-20" ></a><img src="https://ir-na.amazon-adsystem.com/e/ir?t=vmw0a-20&l=li2&o=1&a=B0765HSPB6" width="1" height="1" border="0" alt="" style="border:none !important; margin:0px !important;" />
</td>

ESP makes dumb wired door sensors to a smart sensor by sending MQTT signals to HA notifing its current state.
The Aura system uses Wifi waves to detect motion through walls.  It covers the entire house.  Scenes are activated via IFTTT/HA integration.

- Shut down HVAC system if a Window or Door is left open for more than 5 minutes.
- Play chime on all window and door open/closes.
- Change Aura scenes based on presence and sleep.


## Docker containers/Addons
- Home Assistant: Home automation software
- Configurator: Browser-based configuration file editor for Home Assistant
- Dasher: a service allowing Amazon Dash buttons to interact with the system
- SmartThings Bridge: Bridge for pairing Hass.io and Samsung SmartThings.
- Grafana: data visualization and analytics
- Mosquitto: an MQTT broker for fast, friendly service communication

## Resources
 ######  For inspiration or configuration visit following Repos/Youtube GURUS if you haven't already.
 ###### Also Be sure to 🌟 their repo!!!

- [CCOSTAN](https://github.com/CCOSTAN/Home-AssistantConfig) - I mostly follow him for Floorplan and package setup. Probably the best documented configuration out there. Star his repo if you havent already
- [stanvx](https://github.com/stanvx/Home-Assistant-Configuration) - He is all about Xiaomi products and has really good examples for automation and Floorplan.
- [notoriousbdg](https://github.com/notoriousbdg/hassio-addons) - notoriousbdg has a great repo with add-ons for Node-Red, HA Bridge & Gogs.
- [BRUH Automation](https://www.youtube.com/channel/UCLecVrux63S6aYiErxdiy4w) - Great place for video tutorials on HA related guides.
- [DrZzs](https://www.youtube.com/channel/UC7G4tLa4Kt6A9e3hJ-HO8ng) - For anyone wanting to use Sonoff switches & ESP8266, plenty of useful guides.
- [HA Podcast](https://hasspodcast.io/) - if you are lazy to read about changes to Home Automation in a new version this is a really good podcast to hear while driving
