---
layout: tag
title: Tutorials
filterable: 
- tutorials
permalink: tutorials
---

{% assign tutorials = site.posts | where: "category", "tutorials" %}
{% assign tags = tutorials | map: "tags" | uniq %}

<div id="keywords">
    {% for tag in tags %}
    <div class="tag_outline inline-flex">
        <div class="inline-flex items-center px-2.5 py-1.5 rounded-full text-xs font-medium bg-indigo-100">
        <a class="!no-underline" href="{{site.baseurl}}/tag#{{ tag }}">{{ tag }}</a>
        </div>
    </div>
    {% endfor %}
</div>

<div id="tutorials">
  {% for tutorial in tutorials %}
    <div class="py-1" data-tags="{{tutorial.tags | join: ' ' | upcase }}" data-title="{{tutorial.about | upcase}}">
      <h3><a href="{{site.baseurl}}{{ tutorial.url }}">{{ tutorial.title}}</a></h3>
      <div class="text-sm text-gray-400"  data-tags="{{tutorial.tags | join: ' ' | upcase }}" data-title="{{tutorial.about | upcase}}">{{tutorial.about}}</div>
    </div>
  {% endfor %}
</div>

