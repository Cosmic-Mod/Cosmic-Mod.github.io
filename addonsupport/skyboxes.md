---
title: Skyboxes
layout: page
show_sidebar: false
menubar: docs_menu
---

Skybox data is a JSON object, commonly used in [solar system data](/addonsupport/solarsystems) or [planet data](/addonsupport/planets).

### Attributes:

`"attached_skybox_texture_id"`: string, name of a texture in …/assets/cosmic/textures (file extension not needed)

`"yaw"`: int, yaw of the skybox texture

`"pitch"`: int, pitch of the skybox texture

`"roll"`: int, roll of the skybox texture

`"alpha"`: int, from 0 to 255. Transparency of the skybox. Behind the skybox is simply sky fog. 0 is no skybox visible, 255 is no fog visible.

`"rotation_plane"`: string, can be either "yaw", "pitch" or "roll". Controls which axis the skybox will rotate around. (Optional)

`"fade"`: string, can be "day" or "night". Defines when the skybox will fade away. (Optional)

`"vanilla_sunlight"`: boolean, controls weather the sunlight color will be vanilla or not. 

`"sunlight_color"`: JSON object, must be included if `"vanilla_sunlight"` is false. Must include the following:

{% capture light_data %}

"r": int, from 0 to 255. Controls the red in the sunlight color

"g": int, from 0 to 255. Controls the green in the sunlight color

"b": int, from 0 to 255. Controls the blue in the sunlight color

"alpha": int, from 0 to 255. Controls the transparency of the sunlight. Basically the brightness of the sunlight. 255 is full brightness, 0 is darkness.

{% endcapture %} {% include spoiler.html name="Sunlight color" content=light_data %}
