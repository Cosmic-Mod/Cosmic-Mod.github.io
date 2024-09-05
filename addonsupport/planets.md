---
title: Planets
layout: page
show_sidebar: false
menubar: docs_menu
---

Planet data is a json object, usually embedded into a solar system file.
## Valid attributes:

### Basic info, e.g. position:
`xpos`: integer, X position of the planet

`ypos`: integer, Y position of the planet

`zpos`: integer, Z position of the planet

`yaw`: integer, yaw of the planet

`pitch`: integer, pitch of the planet

`roll`: integer, roll of the planet

`scale`: integer, size of the planet

### Visual info, e.g. texture:

`texture_id`: string, the name of a texture file located in `../assets/cosmos/textures/` (file extension is not needed)

`glowing`: boolean, whether the planet is glowing

{% capture glowing_data %}
#### If glowing is true the following info is required:

`core_color`: dictionary, needs "r", "g" and "b" keys with integer values from 0 to 255

`bloom_color`: dictionary, needs "r", "g" and "b" keys with integer values from 0 to 255

The core color controls the inner color of the glowing object. Most stars use 255 for everything.

The bloom color represents the outer bloom color. A black hole uses 0, 0, 0 for core and 255, 255, 255 for bloom.

`layer`: integer, controls how detailed the planets glow is. 64 is recommended

***
{% endcapture %}
{% include spoiler.html name="Glowing data" content=glowing_data %}

`ringed`: boolean, controls whether the planet has rings


{% capture ringed_data %}
#### If ringed is true the following info is required:

`"ring_data"`: dictionary, contains unlimited ring objects specified with string names

e.g.

`"ring_data": {`

  `"ring1": {ringdata},`

  `"ringtwo": {ringdata}`

`}`

A ring must have the following:

`"texture_id"`: string, the name of a texture file located in `../assets/cosmos/textures/` (file extension is not needed)

`"radius"`: integer, radius from centre of planet. Required for distance calculations

`"scale_radius"`: integer, todo: figure this out

`"flip_y"`: boolean, see more info below

`"flip_x"`: boolean, see more info below

`"flip_z"`: boolean, see more info below

// since rings can be tilted. logic for it has been added.

use the best suited logic.

flip_y: it is used for flat rings as in for saturn in thhe mod. 
flip_x
flip_z

// flip the axis which you think the ring faces the most. so multiple flips can be done as well
// for genral data uranus rings are flipped to x

//radius indicates radius from centre of main object. this is required for distance calculation but can be played with
// scale radius indicates the size of rings individually not planetR+(scaleradius)

***
{% endcapture %}
{% include spoiler.html name="Ringed data" content=ringed_data %}

`attached_dimention_id`: string, todo: figure out

`skybox_data`: dictionary, contains the skybox?
