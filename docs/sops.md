---
layout: tag
title: Standard Operating Procedures (SOPs)
filterable: 
- sops
permalink: sops
---

{% assign sop_posts = site.posts | where: "category", "sops" %}
{% assign tags = sop_posts | map: "tags" | uniq %}

<div id="keywords">
    {% for tag in tags %}
    <div class="tag_outline inline-flex">
        <div class="inline-flex items-center px-2.5 py-1.5 rounded-full text-xs font-medium bg-indigo-100">
        <a class="!no-underline" href="{{site.baseurl}}/tag#{{ tag }}">{{ tag }}</a>
        </div>
    </div>
    {% endfor %}
</div>

<div id="sops">
  {% for sop in sop_posts %}
    <div class="py-1" data-tags="{{sop.tags | join: ' ' | upcase }}" data-title="{{sop.about | upcase}}">
      <h3><a href="{{site.baseurl}}{{ sop.url }}">{{ sop.title}}</a></h3>
      <div class="text-sm text-gray-400" data-tags="{{sop.tags | join: ' ' | upcase}}" data-title="{{sop.about | upcase}}">{{sop.about}}</div>
    </div>
  {% endfor %}
</div>

