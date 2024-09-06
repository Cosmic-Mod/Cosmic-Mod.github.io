---
title: Solar Systems
layout: page
show_sidebar: false
menubar: docs_menu
---

Solar system files are stored under the cosmic namespace, in the cosmic_data folder. 

> data
> > your_namespace
> > > etc

> > cosmos
> > > cosmic_data
> > > > solar_system_1.json
> > > > solar_system_2.json
> > > > etc


## Attributes
`"planet_data"`: JSON object, see the page on planet data

`"attached_dimention_id"`: string, must be a namespace:name linking to a valid dimension

`"skybox_data"`: JSON object, see the page on Skybox data

`“dimensional_data"`: JSON object, see the page on dimensional data

`"gui_data"`: JSON object, see below

{% capture gui_data %}

### Gui data

`"category_"`: JSON object, Creates a new GUI tab for this category in this system. Commonly used for multi-star systems. Must contain the following:

### Category objects

`"travel_dimension"`: string, the dimension players are teleported to when using this GUI. Should usually be the same as `"attached_dimention_id"`

`"origin_x"`: int, the x coordinate players will be teleported to when entering this dimension

`"origin_y"`: int, same as above but y coordinate

`"origin_z"`: int, same as above but z coordinate

`"unlocking_dimension"`: string, a dimension id that will unlock this dimension for travelling

`"background"`: string, name of a texture in …/assets/cosmic/textures (file extension not needed)

`"title"`: string, the title to be displayed for this category

`"order"`: int, the position of this category in the GUI tabs section. From least to most. (This position is global between all systems and datapacks)

`"object_data"`: JSON object, contains unlimited GUI "planet" objects specified with string names

e.g.

```
"object_data": {
  "planet1_": {guiplanet},
  "planet2_": {guiplanet}
}
```

### Gui planet objects

Each guiplanet object must contain the following:

`"texture_id"`: string, name of a texture in …/assets/cosmic/textures (file extension not needed)

`"scale"`: int, size of mini planet in list of planets (Usually about 15)

`"ponder_scale"`: int, size of planets when viewing its stats (usually about 60)

`"yaw"`: int, yaw of mini planet

`"pitch"`: int, pitch of mini planet

`"roll"`: int, roll of mini planet

`"yaw_speed"`: int, speed at which the mini planet rotates on yaw. Usually between 0 and 1

`"pitch_speed"`: int, same as above but pitch

`"roll_speed"`: int, same as above but roll

`"travel_x"`: int, x coordinates in space dimension player is taken to when fast travelling to this planet. Ideally should _not_ be inside the planet and should take the player simply close by

`"travel_y"`: int, same as above but y coordinates

`"travel_z"`: int, same as above but z coordinates

`"unlocking_dimension"`: string, the dimension id at which fast travel to this planet is unlocked. Should usually be the dimension of this planet

`"atmosphere"`: JSON object, see the page on fancy JSON text

`"name"`: JSON object, see the page on fancy JSON text

`"type"`: JSON object, see the page on fancy JSON text

`"conditions"`: JSON object, see the page on fancy JSON text

`"size"`: JSON object, see the page on fancy JSON text

`"category"`: JSON object, see the page on fancy JSON text

"life": float, percent of life being on this planet betweeen 0 and 1 (purely GUI, will not affect spawn rates)

`"ringed"`: boolean, whether the mini-planet has rings

### Ring data

If ringed is true, the following is required:

`"ring_data"`: JSON object, contains unlimited ring objects specified with string names

e.g.

"ring_data": {

"ring1_": {guiringdata},

"ring2_": {guiringdata}

}

A gui ring data object must have the following:

`"texture_id"`: string, the name of a texture file located in ../assets/cosmos/textures/ (file extension is not needed)

`"scale_radius"`: integer, radius from planet the center of the ring is

{% capture example_gui_data %}

```
"ring_data": {
  "B1400_sys": {
      "object_data": {
          "planet1": {
            "texture_id": "p1tex",
            "scale": 0.3,
            "ponder_scale": 1.42,
            "yaw": 24,
            "pitch": -165,
            "roll": 10,
            "yaw_speed": 0.03,
            "pitch_speed": 0,
            "roll_speed": 0,
            "travel_x": -152000,
            "travel_y": 2080,
            "travel_z": 300,
            "unlocking_dimension": "cosmos:planet_1_dim",
            "atmosphere": {
                "text": "None",
                "color": "light_gray"
            },
            "name": {
                "text": "Planet 1",
                "color": "orange"
            },
            "type": {
                "text": "Gas",
                "color": "pink"
            },
            "conditions": {
                "text": "Harsh",
                "color": "purple"
            },
            "size": {
                "text": "Ginormous",
                "color": "red"
            },
            "category": {
                "text": "Gas Giant",
                "color": "orange"
            },
            "life": 0,
            "ringed": true,
            "ring_data": {
                "ring1": {
                  "texture_id": "jb1",
                  "scale_radius": 0.675
                },
                "ring2": {
                  "texture_id": "jb2",
                  "scale_radius": 1.5
                }
            }
          },
          "planet2": {
            "texture_id": "p2tex",
            "scale": 14.5,
            "ponder_scale": 58,
            "yaw": 17,
            "pitch": -195,
            "roll": -4,
            "yaw_speed": 0.55,
            "pitch_speed": 0,
            "roll_speed": 0,
            "travel_x": -145200,
            "travel_y": 600,
            "travel_z": 32730,
            "unlocking_dimension": "cosmos:planet_2_dim",
            "atmosphere": {
                "text": "None",
                "color": "light_gray"
            },
            "name": {
                "text": "Planet 2",
                "color": "green"
            },
            "type": {
                "text": "Rocky",
                "color": "brown"
            },
            "conditions": {
                "text": "Windy",
                "color": "magenta"
            },
            "size": {
                "text": "Dwarf",
                "color": "lime"
            },
            "category": {
                "text": "Satellite",
                "color": "light_gray"
            },
            "life": 0,
            "ringed": false
        }
      },
      "travel_dimension": "cosmos:b_1400_dim",
      "origin_x": -40000,
      "origin_y": 420,
      "origin_z": 0,
      "unlocking_dimension": "cosmos:solar_sys_d",
      "background": "gui_bg",
      "title": "B1400 System",
      "order": -2
  }
}
```

{% endcapture %} {% include spoiler.html name="Example" content=example_gui_data %}

{% endcapture %} {% include spoiler.html name="Gui data" content=gui_data %}
