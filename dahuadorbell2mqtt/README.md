# Home Assistant Add-on: Dahua VTO to MQTT Broker

Sends Dahua Intercom events to the MQTT Broker

![Supports aarch64 Architecture][aarch64-shield] ![Supports amd64 Architecture][amd64-shield] ![Supports armhf Architecture][armhf-shield] ![Supports armv7 Architecture][armv7-shield] ![Supports i386 Architecture][i386-shield]

## Installation

The installation of this add-on is straightforward and easy to do.

1. Navigate in your Home Assistant frontend to **Supervisor** -> **Add-on Store**.
2. Add a new repository by URL `https://github.com/cibernox/home-assistant-addons`
3. Find the "DahuaDoorbell2MQTT" add-on and click it.
4. Click on the "INSTALL" button.

## How to use

To use this add-on, you need to supply the config for your intercom and MQTT Broker

- Requires you to use one of the supported Dahua Intercoms
- Requires you to run a local MQTT server
- [DahuaDoorbell2MQTT's documentation][documentation]


## Configuration

Add-on configuration:

```json
{
    "intercom": {
      "host": "192.168.1.110",
      "username": "admin",
      "password": "admin"
    },
    "mqtt": {
      "host": "core-mosquitto",
      "port": "1883",
      "username": "homeassistant",
      "password": "homeassistant",
      "topic_prefix": "DahuaVTO"
    }
}
```

## Known issues and limitations

- None. Let me know.

## Credits
This project is a port to Node.js of [elad-bar/DahuaVTO2MQTT](https://github.com/elad-bar/DahuaVTO2MQTT). That addon was written in PHP and I
decided to convert it to node and clarify the code along the way so it's more approachable for contributors.
His work was in turn based on [riogrande75's][original-author] PHP code that connects your intercom and publishes events via MQTT broker.

I didn't invent anything here, I stand on the shoulder of giants.
