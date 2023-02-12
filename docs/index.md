---
layout: home
title: Home
permalink: /
---

{% assign posts = site.posts | sort: 'lastUpdated' | reverse %}

<div id="posts">
  <h2>Recently-Added</h2>
  {% for post in posts limit: 5 %}
    <div class="py-1" data-tags="{{post.tags | join: ' ' | upcase }}" data-title="{{post.about | upcase}}">
      <h3><a href="{{site.baseurl}}{{ post.url }}">{{post.title}} ({{post.lastUpdated | date: "%Y-%m-%d" }})</a></h3>
      <div class="text-sm text-gray-400" data-tags="{{post.tags | join: ' ' | upcase }}" data-title="{{post.about | upcase}}">{{post.about}}</div>
    </div>
  {% endfor %}
</div>