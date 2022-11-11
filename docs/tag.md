---
layout: tag
title: Keywords
filterable: 
- posts 
permalink: tag
---

{% assign tags = site.tags %}

<div id="keywords">
    {% for tag in tags %}
    <div class="tag_outline inline-flex">
        <div class="inline-flex items-center px-2.5 py-1.5 rounded-full text-xs font-medium bg-indigo-100">
        <a class="!no-underline" href="{{site.baseurl}}/tag#{{ tag[0] }}">{{ tag[0] }}</a>
        </div>
    </div>
    {% endfor %}
</div>

<div id="posts">
{% for tag in tags %}
  {% assign all_about = tag[1] | map: "about" %}
  <!-- divider -->
  <div class="relative my-8"  data-tags="{{tag[0]| upcase }}" data-title="{{ all_about | join: ' ' | upcase }}">
    <div class="absolute inset-0 flex items-center" aria-hidden="true"   data-tags="{{tag[0]| upcase }}" data-title="{{ all_about | join: ' ' | upcase }}">
      <div class="w-full border-t border-gray-200"   data-tags="{{tag[0]| upcase }}" data-title="{{ all_about | join: ' ' | upcase }}"></div>
    </div>
    <div class="relative flex justify-center "   data-tags="{{tag[0]| upcase }}" data-title="{{ all_about | join: ' ' | upcase }}">
      <span class="bg-white px-2 text-gray-200">
        <i class="text-xs far fa-square"></i>
      </span>
    </div>
  </div>
  <!-- /divider -->

  
  <div class="inline-flex items-center px-2.5 py-2.5 rounded-full text-s font-medium bg-indigo-100"   data-tags="{{tag[0]| upcase }}" data-title="{{ all_about | join: ' ' | upcase }}">
      <a class="!no-underline" id="{{ tag[0] }}">{{ tag[0] }}</a>
  </div>
  
  <div   data-tags="{{tag[0] | upcase }}" data-title="{{ all_about | join: ' ' | upcase }}">
    <ul    data-tags="{{tag[0]| upcase }}" data-title="{{ all_about | join: ' ' | upcase }}">
      {% for post in tag[1] %}
        <li    data-tags="{{tag[0]| upcase }}" data-title="{{ post.about | upcase }}">
          <div class="text-sm text-gray-400"   data-tags="{{tag[0]| upcase }}" data-title="{{ post.about | upcase }}">
            <a href="{{site.baseurl}}{{ post.url }}">{{ post.title }}</a> - 
            {{post.about}}
          </div>
        </li>
      {% endfor %}
    </ul>
  </div>
  
{% endfor %}
</div>


{% include footer.html %}