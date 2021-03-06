---
title: "Logbook Card"
sidebar_label: Logbook
description: "The Logbook card displays entries from the logbook for specific entities."
---

The Logbook card displays entries from the logbook for specific entities.

<p class='img'>
  <img src='/images/lovelace/lovelace_logbook.png' alt='Screenshot of the logbook card'>
  Screenshot of the Logbook card.
</p>

To add the Logbook card to your user interface, click the Lovelace menu (three dots at the top right of the screen) and then **Edit Dashboard**. Click the plus button in the bottom right corner and select **Logbook** from the card picker.

### Card Settings


{% configuration_basic %}
Entities:
  description: The entities whose logbook entries will show in the card.
Title:
  description: The title that shows on the top of the card.
Hours to show:
  description: The number of hours in the past that will be tracked in the card.
Theme:
  description: Theme your card using any installed theme in your HA environment.
{% endconfiguration_basic %}

### YAML

This is for if you use YAML mode or prefer to use YAML in the Code Editor in the UI.

{% configuration %}
type:
  required: true
  description: logbook
  type: string
entities:
  required: true
  description: "The entities that will show in the card."
  type: list
title:
  required: false
  description: Title of the card.
  type: string
hours_to_show:
  required: false
  description: Number of hours in the past to track.
  type: integer
  default: 24
theme:
  required: false
  description: "Set to any theme within `themes.yaml`."
  type: string
{% endconfiguration %}

Example:

```yaml
type: logbook
entities:
  - fan.ceiling_fan
  - fan.living_room_fan
  - light.ceiling_lights
hours_to_show: 24
```
