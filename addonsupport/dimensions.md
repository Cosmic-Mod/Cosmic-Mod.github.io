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

`"weather_data"`: JSON object, optional. `"weather"` must be false for this setting to work. This setting will override vanilla rain/snow for custom particles, sounds etc. Must contain the following:

{% capture weather_data %}

`"condition"`: string, must be "rain", "snow" or "none". Controls when the custom weather will render.

`"texture_id"`: the name of the texture in assets/cosmos/... to be used for the particles

`"speed"`: float, the speed of the weather. Vanilla snow is 0.5, and vanilla rain is 2.

`"sound_generic"`: string, the sound played when the player is in an open area with this weather. Should be the name of a sound as shown with the /playsound command. (e.g. block.snow.fall)

`"sound_special"`: string, same as above, but will be player when the player is in an inclosed space instead. E.g. a house or a cave.

`"power"`: int, basically the volume of this weather. Recommended to be 1-5

`"hurt"`: boolean, controls whether the weather will hurt players. (E.g. acid rain)

`"damage"`: int, only needed if `"hurt"` is true. Controls the damage the weather does to the player. Each 1 is half a heart, so 5 would be 2 hearts and a half.

{% endcapture %} {% include spoiler.html name="Weather data" content=weather_data %}

`"atmospheric_data"`: JSON object, optional. If not included, will default to overworld. If included, must contain the following:

{% capture atmo_data %}

`"atmosphere_y"`: int, the Y level where players will be transported to space.

`"travel_to"`: string, the dimension players will be transported to on reaching the `"atmosphere_y"`. Usually the solar system dimension this planet is in. Should be in `namespace:dimension` form.

`"origin_x"`: int, the x position players will be sent to on entering this planet by default

`"origin_y"`: int, same as above but y position

`"origin_z"`: int, same as above but z position

`"overlay_texture_id"`: string, the name of a texture in assets/cosmos/... Will be used for the sidebar showing height progress when launching a rocket. MUST be 16x128 

`"shipbit_y"`: int, the offset of pixels from the bottom of the overlay image that will be the lowest point the ship icon can reach. 

`"ship_min_y"`: int, the y position at which the rocket icon will be at the lowest point, at `"shipbit_y"` on the overlay texture

{% endcapture %} {% include spoiler.html name="Atmospheric data" content=atmo_data %}
