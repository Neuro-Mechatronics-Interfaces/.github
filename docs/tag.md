---
layout: tag
title: Keywords
permalink: tag
---

<div>
{% for tag in site.tags %}
  <!-- <h2 id="{{ tag[0] }}">{{ tag[0] }}</h2> -->
  <div class="inline-flex items-center px-2.5 py-2.5 rounded-full text-s font-medium bg-indigo-100 text-indigo-800 hover:bg-slate-900 hover:text-sky-100">
      <a class="!no-underline" id="{{ tag[0] }}">{{ tag[0] }}</a>
    </div>
  <ul>
    {% for post in tag[1] %}
      <li><a href="{{site.baseurl}}{{ post.url }}">{{ post.title }}</a></li>
      <div class="text-sm text-gray-400">{{post.about}}</div>
    {% endfor %}
  </ul>
  <!-- divider -->
  <div class="relative my-8">
    <div class="absolute inset-0 flex items-center" aria-hidden="true">
      <div class="w-full border-t border-gray-200"></div>
    </div>
    <div class="relative flex justify-center ">
      <span class="bg-white px-2 text-gray-200">
        <i class="text-xs far fa-square"></i>
      </span>
    </div>
  </div>
{% endfor %}
</div>


{% include footer.html %}