---
layout: tag
title: Examples
filterable:
- examples
permalink: examples
---

{% assign examples = site.posts | where: "category", "examples" %}
{% assign tags = examples | map: "tags" | uniq %}

<div id="examples">
  {% for example in examples %}
    <div class="py-1" data-tags="{{example.tags | join: ' ' | upcase }}" data-title="{{example.about | upcase}}">
      <h3><a href="{{site.baseurl}}{{ example.url }}">{{ example.title}}</a></h3>
      <div class="text-sm text-gray-400" data-tags="{{example.tags | join: ' ' | upcase }}" data-title="{{example.about | upcase}}">{{example.about}}</div>
    </div>
  {% endfor %}
</div>

