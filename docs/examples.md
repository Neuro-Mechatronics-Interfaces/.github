---
layout: page
title: Examples
permalink: examples
---

<div>
  {% assign example_posts = site.posts | where: "category", "examples" %}
  {% for example in example_posts %}
    <div class="py-1">
      <h3><a href="{{site.baseurl}}{{ example.url }}">{{ example.title}}</a></h3>
      <div class="text-sm text-gray-400">{{example.about}}</div>
    </div>
  {% endfor %}
</div>

