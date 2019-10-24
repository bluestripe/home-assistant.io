---
title: "Atlona Juno 451 4x1 HDMI Switch"
description: "Instructions on how to integrate Atlona Juno 4x1 HDMI Switch into Home Assistant."
logo: atlona-logo.png
ha_category:
  - Media Player
ha_release: "0.100"
ha_iot_class: Local Polling
ha_config_flow: false
---

The `atlona_juno` platform allows you to control [Atlona Juno 451 - 4K HDR Four-Input HDMI Switcher](https://atlona.com/product/at-juno-451/) using a http connection.

To add a Atlona Juno device to your installation, add the following to your `configuration.yaml` file:

```yaml
# Example configuration.yaml entry
media_player:
  - platform: atlona_juno
    host: 192.168.10.10
    sources:
      1:
        name: TV
      2:
        name: Nintendo
      3:
        name: PS4
      4:
        name: Plex
```

{% configuration %}
protocol:
  description: The protocol that is being used. 
  default: http.
  required: false
  type: string
host:
  description: The IP address Atlona Juno 451 HDMI Switch.
  required: true
  type: string
port:
  description: IP port that is used. 
  default: 80
  required: false
  type: integer
sources:
  description: The list of sources available. Valid source numbers are 1, 2, 3, 4. Each source number corresponds to the input number on the Atlona Juno 451 HDMI switch. Each source must have a name assigned to it.
  required: true
  type: map
  keys:
    SOURCE_NUMBER:
      name: The name of the source.
      type: string
{% endconfiguration %}
