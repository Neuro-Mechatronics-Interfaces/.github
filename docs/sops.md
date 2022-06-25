---
layout: page
title: Standard Operating Procedures (SOPs)
permalink: sops
---

<div>
  {% assign sop_posts = site.posts | where: "category", "sops" %}
  {% for sop in sop_posts %}
    <div class="py-1">
      <h3><a href="{{site.baseurl}}{{ sop.url }}">{{ sop.title}}</a></h3>
      <div class="text-sm text-gray-400">{{sop.about}}</div>
    </div>
  {% endfor %}
</div>

