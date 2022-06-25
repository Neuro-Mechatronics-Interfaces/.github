---
layout: page
title: Tutorials
permalink: tutorials
---

<div>
  {% assign tutorials = site.posts | where: "category", "tutorials" %}
  {% for tutorial in tutorials %}
    <div class="py-1">
      <h3><a href="{{site.baseurl}}{{ tutorial.url }}">{{ tutorial.title}}</a></h3>
      <div class="text-sm text-gray-400">{{tutorial.about}}</div>
    </div>
  {% endfor %}
</div>

