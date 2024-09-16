---
title: Planet infos
subtitle: Info on each planet
layout: page
---
{% include three.html id="saturn_stats" path="/assets/models/" model="saturn.gltf" %}

{% capture saturn %}
Location: -65000, 1475, 30000

Scale: 1450

Gui scale: 10.3

Gui "ponder" scale: 47

Rings: true

Ring radius: 1500

Ring scale radius: 3500

Dimension: `cosmos:saturn_lands`
{% endcapture %} {% include spoiler.html name="### Saturn" content=saturn %}


