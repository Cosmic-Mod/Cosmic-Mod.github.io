---
title: Fancy text in JSON
layout: page
show_sidebar: false
menubar: docs_menu
---

Some parts in your datapack may require some stylised text.
Unfortunatly, at this time Cosmic Horizons doesn't support vanilla JSON text objects.
However, it does come with its own.

They are JSON dictionarys/objects with two keys.

Note that unlike vanilla text objects, these _cannot_ be combined in a list to have multiple colors.

**This is invalid:**
```
"name": [
  {
    "text": "red ",
    "color": "red"
  },
  {
    "text": "blue",
    "color": "blue"
  }
]
```
However this is fine:
```
"name": {
  "text": "Only red",
  "color": "red"
}
```


`"text"`: string, the text that the object is

`"color"` string, technically an enum. _Must be all lowercase_, and be a color from this list:

- red
- orange
- yellow
- green
- lime
- cyan
- light blue
- blue
- magenta
- purple
- pink
- brown
- gray
- light gray
- black
- white

