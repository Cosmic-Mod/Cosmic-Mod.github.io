---
title: Dimensions
layout: page
show_sidebar: false
menubar: docs_menu
---

Dimension data is commonly used in a [solar system file](/addonsupport/solarsystems/) to set the dimension settings. It will also be used to set the settings of a [planet](/addonsupport/planets)*

## Attributes:

`"dimension_type"`: string, can be "space" or "planet"

`"sky_objects"`: boolean, if false it will disable vanilla stars, sun and moon for this dimension. If not included, will default to true.

`"weather"`: boolean, controls whether or not the the dimension will have vanilla rain and snow. If not included, will default to true.

`"clouds"`: boolean, controls whether or not the dimension will have clouds. If not included, will default to true.

`"gravity"`: float or int, is the percentage of earths gravity the dimension will have. Can be 0.1 for 10% or 10 for 10%. If not included, will default to 100 (vanilla overworld).

`"air_resistance"`: float, in the range of 0 to 1. Don’t let the name confuse you, 0 is maximum friction in the air and 1 is none. 1 will simulate space where when floating you have no control over your character, whereas 0 will prevent players from moving at all in the air. If not included, will default to 0 (vanilla).

`"fog_data"`: JSON object, optional. If not included, will default to vanilla. If included, must contain the following:

{% capture fog_data %}

`"color"`: JSON object, must contain a "r", "g" and "b" key, each giving an int between 0 and 255 to control the fog color

Example:
```json
"color": {
  "r": 255,
  "b": 255,
  "g": 255
}
```

`"level"`: float, controls the density of the fog. 0.1 is vanilla.

{% endcapture %} {% include spoiler.html name="Fog data" content=fog_data %}

