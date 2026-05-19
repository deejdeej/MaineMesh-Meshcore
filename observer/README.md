# MaineMesh Meshcore Observers

Observers play a critical role in helping to monitor the overall health and status of the mesh network.

We participate in three mesh monitors, [LetsMesh](https://letsmesh.net), [Meshmapper](https://bgr.meshmapper.net/), and the [New England Live Map](https://map.newenglandme.sh/map?lat=45.34869&lon=-69.58150&zoom=8&layer=dark&history=off&heat=off&coverage=off&weather=off&weather_radar=on&weather_wind=on&labels=off&nodes=on&legend=on&menu=on&units=mi&history_filter=0&route_bytes=all).

Within Meshmapper we've established a state wide region BGR (Bangor) to allow monitoring of all traffic within the state.  If you choose to setup a Meshcore observer, please set the region to BGR to help us out!


## Configuration

To setup an observer, follow the directions on the [Meshmapper Observer Setup](https://wiki.meshmapper.net/mqtt-main/) site using one of the observer methods described there.

Set the IATA region to BGR
```
# Location Code
PACKETCAPTURE_IATA=BGR
```

At the MQTT Broker Configuration stage, configure a total of three brokers:

```
# MQTT Broker 1 - LetsMesh.net Packet Analyzer (US)
PACKETCAPTURE_MQTT1_ENABLED=true
PACKETCAPTURE_MQTT1_SERVER=mqtt-us-v1.letsmesh.net
PACKETCAPTURE_MQTT1_PORT=443
PACKETCAPTURE_MQTT1_TRANSPORT=websockets
PACKETCAPTURE_MQTT1_USE_TLS=true
PACKETCAPTURE_MQTT1_USE_AUTH_TOKEN=true
PACKETCAPTURE_MQTT1_TOKEN_AUDIENCE=mqtt-us-v1.letsmesh.net
PACKETCAPTURE_MQTT1_KEEPALIVE=120

# MQTT Topics for Broker 1 - Default Pattern
PACKETCAPTURE_MQTT1_TOPIC_STATUS=meshcore/{IATA}/{PUBLIC_KEY}/status
PACKETCAPTURE_MQTT1_TOPIC_PACKETS=meshcore/{IATA}/{PUBLIC_KEY}/packets

# MQTT Broker 2
PACKETCAPTURE_MQTT2_ENABLED=true
PACKETCAPTURE_MQTT2_SERVER=mqtt.meshmapper.net
PACKETCAPTURE_MQTT2_PORT=443
PACKETCAPTURE_MQTT2_TRANSPORT=websockets
PACKETCAPTURE_MQTT2_USE_TLS=true
PACKETCAPTURE_MQTT2_USE_AUTH_TOKEN=true
PACKETCAPTURE_MQTT2_TOKEN_AUDIENCE=mqtt.meshmapper.net

# MQTT Topics for Broker 2 - Default Pattern
PACKETCAPTURE_MQTT2_TOPIC_STATUS=meshcore/{IATA}/{PUBLIC_KEY}/status
PACKETCAPTURE_MQTT2_TOPIC_PACKETS=meshcore/{IATA}/{PUBLIC_KEY}/packets

# MQTT Broker 3
PACKETCAPTURE_MQTT3_ENABLED=true
PACKETCAPTURE_MQTT3_SERVER=mqttmc01.bostonme.sh
PACKETCAPTURE_MQTT3_PORT=443
PACKETCAPTURE_MQTT3_TRANSPORT=websockets
PACKETCAPTURE_MQTT3_USE_TLS=true
PACKETCAPTURE_MQTT3_USE_AUTH_TOKEN=true
PACKETCAPTURE_MQTT3_TOKEN_AUDIENCE=mqttmc01.bostonme.sh

# MQTT Topics for Broker 3 - Default Pattern
PACKETCAPTURE_MQTT3_TOPIC_STATUS=meshcore/{IATA}/{PUBLIC_KEY}/status
PACKETCAPTURE_MQTT3_TOPIC_PACKETS=meshcore/{IATA}/{PUBLIC_KEY}/packets
```
