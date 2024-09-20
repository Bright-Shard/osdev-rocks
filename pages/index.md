---
permalink: /
layout: default
title: Home
no-toc: true
---

Welcome to osdev.rocks - a modern wiki for operating system developement! This wiki is very new, and therefore very much a work-in-progress. It aims to offer similar information as the [OSDev Wiki](https://wiki.osdev.org), but in a more concise and less confusing manner. The wiki will start off only documenting the x86 architecture, but plans to expand to others later. You can contribute information and expand the wiki [from its GitHub](https://github.com/bright-shard/osdev-rocks)!

# Pages

{% for page in site.pages %}
- [{{ page.title }}]({{ page.permalink }})
{% endfor %}
