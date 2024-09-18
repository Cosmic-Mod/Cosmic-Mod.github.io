---
title: Sky data
layout: page
show_sidebar: false
menubar: docs_menu
---

Sky data is used in planet or dimension [cosmic data files](/addonsupport/cosmicdata/), to specify a custom skybox with planets.

It can have as many keys as you want, each containing the attributes below. Each key is basically a "planet" for the sky. 
Note that for layering, the first "planet" in the dictionary will be treated as furthest away and not be rendered on top of other "planets" later. 
So you should add your planets from furthest to nearest in order in this dictionary.

## Attributes:

`"type"`: string, must be "object" or "ring". Objects are "planets" for the sky, whereas rings are for rings around the current planet.

{% capture object_data %}

`"phased"`: boolean, controls whether this planet will have phases like the vanilla moon. The planet will be rotated 60 degrees according to the current phases of the moon.
  		
`"object_yaw"`: int, the yaw of the "planet" model

`"object_pitch"`: int, same as above but pitch

`"object_roll"`: int, same as above but roll

`"yaw"`: int, initial yaw the "planet" is rotated around its parent planet/dimension. Basically its initial position in the sphere that is the sky

`"pitch"`: int, same as above but pitch

`"roll"`: int, same as above but roll

`"yaw_speed"`: int, speed at which the "planet" is rotated around its parent planet/dimension on the yaw axis

`"pitch_speed"`: int, same as above but pitch

`"roll_speed"`: int, same as above but roll

`"scale"`: float, size of the "planet". Default overworld sun is 0.14

`"texture_id"`: string, the name of a texture in assets/cosmos/... If not included, this "planet" will be assumed to be a star and `"core_color"` and `"bloom_color"` will be required.

`"core_color"`: JSON object, contains "r", "g" and "b" with int values between 0 and 255 controlling the color. For more info, see [planet_data: glowing_data](/addonsupport/planets/)

`"bloom_color"`: JSON object, Same as above, but bloom instead of core. For more info, see [planet_data: glowing_data](/addonsupport/planets/)

`"ring_data"`: JSON object, same as said in [planet_data: ring_data](/addonsupport/planets/). Optional.

{% endcapture %} {% include spoiler.html name="'Object' type attributes" content=object_data %}

{% capture ring_data %}

`"yaw"`: int, yaw of ring around parent planet/dimension.

`"pitch"`: int, same as above but pitch

`"roll"`: int, same as above but roll

`"ring_data"`: JSON object, must contain the following:

`"texture_id"`: string, name of a texture in assets/cosmos/...

`"additive"`: boolean, controls whether the ring will have a "holographic" affect. Used for planets with atmosphere

`"scale_radius"`: float, size of ring. Usually about 0.05.

{% endcapture %} {% include spoiler.html name="'Ring' type attributes" content=ring_data %}

      
