---
title: Cosmic data
layout: page
show_sidebar: false
menubar: docs_menu
---

Most parts of the datapack system all stem from the same files. JSON files in the cosmic data section of a datapack.

They are stored under the cosmic namespace, in the cosmic_data folder. 

> data
> > your_namespace
> > > etc

> > cosmos
> > > cosmic_data
> > > > solar_system_1.json
> > > > 
> > > > solar_system_2.json
> > > > 
> > > > planet_1.json
> > > >
> > > > planet_2.json
> > > >
> > > > overworld.json
> > > >
> > > > other_dimension.json

While all of these files are simply a "cosmic dimension data" file, they are commonly in two forms.

Either used to [setup a space dimension](/addonsupport/solarsystems/), or used to [configure settings for a planet/dimension](/addonsupport/dimensions/).

They will always include an `"attached_dimention_id"`, specifying which dimension they control.

In the file system example, `solar_system_1` and `solar_system_2` are set up as solar system files. They contain a list of planets and what dimensions they go to, GUI data, etc.

`planet_1`, `planet_2`, `overworld`, and `other_dimension` however are all set up as planet/dimension files. This type of file can define a dimensions gravity, custom sky, or space dimension
(dimension that you reach at a certain height). None of these are required, so you may have one dimension file thats just for a custom sky (like `overworld` might be), but another that has custom gravity, space dimension, fog color, etc (like `planet_1` might be).


|                                               | Solar systems | Planets | Dimensions |
|-----------------------------------------------|---------------|---------|------------|
| [attached_dimension_id]()                     | &#9745;       | &#9745; | &#9745;    |
| [planet_data](/addonsupport/planets/)         | &#9745;       | &#9744; | &#9744;    |
| [gui_data](/addonsupport/solarsystems/)       | &#9745;       | &#9744; | &#9744;    |
| [skybox_data](/addonsupport/skyboxes/)        | &#9744;       | &#9745; | &#9745;    |
| [dimensional_data](/addonsupport/dimensions/) | &#9745;       | &#9745; | &#9745;    |


{% capture example_solar %}
```json
{
  "planet_data": {
    //...
  },
  "attached_dimention_id": "cosmos:solar_sys_d",
  "local_id": "Solar Sys.",
  "skybox_data": {
    //...
  },
  "dimensional_data": {
    "dimension_type": "space",
    "weather": false,
    "clouds": false,
    "sky_objects": false,
    "gravity": 0,
    "air_resistance": 1
  },
  "gui_data": {
    "solar_sys": {
      "object_data": {
        //...
      },
      "travel_dimension": "cosmos:solar_sys_d",
      "origin_x": -24100,
      "origin_y": 1000,
      "origin_z": 5100,
      "unlocking_dimension": "none",
      "background": "solar_bg",
      "title": "Solar Sys.",
      "order": -4
    }
  }
}
```
{% endcapture %} {% include spoiler.html name="Example solar system file" content=example_solar %}

{% capture example_planet %}
```json
{
  "attached_dimention_id": "cosmos:marslands",
  "skybox_data": {
    //...
  },
  "dimensional_data": {
    "dimension_type": "planet",
    "weather": false,
    "clouds": false,
    "sky_objects": false,
    "gravity": 38,
    "air_resistance": 0.98,
    "atmospheric_data": {
	    "atmosphere_y": 560,
	    "travel_to": "cosmos:solar_sys_d",
	    "origin_x": -41000,
	    "origin_y": 860,
	    "origin_z": 18000,
	    "overlay_texture_id": "mars_bar",
	    "shipbit_y": 24,
	    "ship_min_y": 120
    }
  },
  "sky_data": {
  	"sun": {
  		"type": "object",
  		"phased": false,
  		"object_yaw": 45,
  		"object_pitch": 40,
  		"object_roll": 35,
  		"yaw": 0,
  		"pitch": 0,
  		"roll": 0,
  		"yaw_speed": 0,
  		"pitch_speed": 0,
  		"roll_speed": 1,
  		"scale": 0.1,
  		"core_color": {
  			"r": 255,
	        "g": 255,
	        "b": 255
        },
         "bloom_color": {
	        "r": 64,
	        "g": 16,
	        "b": 8
        }
  	},
  	"earth": {
  		"type": "object",
  		"phased": false,
  		"texture_id": "earth",
  		"object_yaw": 40,
  		"object_pitch": 30,
  		"object_roll": 20,
  		"yaw": 45,
  		"pitch": 0,
  		"roll": 180,
  		"yaw_speed": 0.5,
  		"pitch_speed": 0,
  		"roll_speed": 1,
  		"scale": 0.008
  	},
  	"saturn": {
  		"type": "object",
  		"phased": false,
  		"texture_id": "saturn",
  		"object_yaw": 45,
  		"object_pitch": 40,
  		"object_roll": 45,
  		"yaw": 0,
  		"pitch": 0,
  		"roll": 180,
  		"yaw_speed": 0,
  		"pitch_speed": 0,
  		"roll_speed": 1,
  		"scale": 0.02,
  		"ring_data": {
  			"ring1": {
  				"texture_id": "sat",
	  			"scale_radius": 0.04,
	  			"radius": 10
  			}
  		}
  	}
  }
}
```
{% endcapture %} {% include spoiler.html name="Example planet file" content=example_planet %}

{% capture example_dim %}
```json
{
  "attached_dimention_id": "minecraft:overworld",
  "skybox_data": {
    //...
  },
  "dimensional_data": {
    "dimension_type": "planet",
    "sky_objects": false,
    "atmospheric_data": {
	    "atmosphere_y": 560,
	    "travel_to": "cosmos:solar_sys_d",
	    "origin_x": -24100,
	    "origin_y": 1000,
	    "origin_z": 5100,
	    "overlay_texture_id": "earth_bar",
	    "shipbit_y": 24,
	    "ship_min_y": 120
    }
  },
  "sky_data": {
  	//...
  }
}
```
{% endcapture %} {% include spoiler.html name="Example dimension with custom sky (e.g. overworld)" content=example_dim %}
