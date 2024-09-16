---
title: Skyboxes
layout: page
show_sidebar: false
menubar: docs_menu
---

Skybox data is a JSON object, commonly used in [solar system data](/addonsupport/solarsystems) or [planet data](/addonsupport/planets).

### Attributes:

`"texture_id"`: string, name of a texture in …/assets/cosmic/textures (file extension not needed)

`"yaw"`: int, yaw of the skybox texture

`"pitch"`: int, pitch of the skybox texture

`"roll"`: int, roll of the skybox texture

`"alpha"`: int, from 0 to 255. Transparency of the skybox. Behind the skybox is simply sky fog. 0 is no skybox visible, 255 is no fog visible.

`"rotation_plane"`: string, can be either "yaw", "pitch" or "roll". Controls which axis the skybox will rotate around. (Optional)

`"fade"`: string, can be "day" or "night". Defines when the skybox will fade away. (Optional)

