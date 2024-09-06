---
title: Contributing
layout: page
show_sidebar: false
menubar: docs_menu
---

Anyone is free to contribute information we may have missed or have gotten wrong. Simply go to the [github repository](https://github.com/Cosmic-Mod/Cosmic-Mod.github.io/tree/main/addonsupport), find the markdown file you want to change in `/addonsupport/`, make a pull request and we will approve it if it’s a good change. 

Keep a few things in mind though to try and keep the wiki consistent
{% capture consistent %}

### JSON

Surround JSON keys with code blocks as well as quotation marks, as they would appear in a file. And please provide a brief overview and what generic type the object is. Also try and seperate the keys per line, you will generally need two new lines for markdown to do so.

`“key”`: int, is a number

`“key2”`: string, can be hello or world

`“key3”`: Boolean, controls whether its on or off

### Embedded objects

You may come across a file that has embedded json objects. What I mean by that is for example:

`“key”`: {

  `“key2”`: int, value,

  `“key3”`: int, value2

}
 
Now when this situation arises, I recommend two things.

If the object has lots of keys, or is used in multiple files (for example dimension data), then make a new wiki page explaining it and simply link the page in the file. So

`“key”`: JSON object, see the page on xyz

OR, if the dictionary is small and not used elsewhere, simply do an embedded block using

< details>

< summary>Xyz data< /summary>

“key2”: int, value

***

< /details>

(Spaces have been added to the beginning to prevent embedding here)

This would turn into:

`“key”`: JSON object, contains the following:

<details>
<summary>key data</summary>

`“key2”`: int, value

`“key3”`: int, also value

***

</details>

{% endcapture %} {% include spoiler.html name="Keeping consistent" content=consistent %}

And here's how to make sure you've done everything:
{% capture gallery %}

TODO

{% endcapture %} {% include spoiler.html name="Adding a gallery photo" content=gallery %}

{% capture doc_page %}

1. Create your markdown page in the /addonsupport/ folder
2. Make sure your markdown header (surrounded in ---) includes:
```
---
title: Your title here
layout: page
show_sidebar: false
menubar: docs_menu
---
```
3. Update `/_data/docs_menu.yml` to include your new site under items as such:
```yml
- label: Docs
  items:
    ...
    - name: Your title here
      link: /addonsupport/your_markdown_file_name_here/
```

{% endcapture %} {% include spoiler.html name="Adding a documentation page" content=doc_page %}
