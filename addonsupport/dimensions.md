---
title: Dimensions
layout: page
show_sidebar: false
menubar: docs_menu
---

Dimension data is commonly used in a solar system file to set the dimension settings. It will also be used to set the settings of a planet*

## Attributes:

`"dimension_type"`: string, can be space or planet*

`"weather"`: boolean, controls whether or not the the dimension will rain and snow

`"clouds"`: boolean, controls whether or not the dimension will have clouds

`"gravity"`: float or int, is the percentage of earths gravity the dimension will have. Can be 0.1 for 10% or 10 for 10%

`"air_resistance"`: float, in the range of 0 to 1. Don’t let the name confuse you, 0 is maximum friction in the air and 1 is none. 1 will simulate space where when floating you have no control over your character, whereas 0 will prevent players from moving at all in the air

***

*planet dimensions have not been implemented yet
