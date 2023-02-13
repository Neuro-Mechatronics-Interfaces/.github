---
layout: home
title: Home
permalink: /
---

{% assign posts = site.posts | sort: 'lastUpdated' | reverse %}
{% assign counter = 0 %}

<div id="posts">
  <h2>Recently-Added</h2>
  {% for post in posts %}
    {% unless post.hidden %}
	  {% if counter < 5 %}
	    <div class="py-1" data-tags="{{post.tags | join: ' ' | upcase }}" data-title="{{post.about | upcase}}">
		  <h3><a href="{{site.baseurl}}{{ post.url }}">{{post.title}} ({{post.lastUpdated | date: "%Y-%m-%d" }})</a></h3>
	      <div class="text-sm text-gray-400" data-tags="{{post.tags | join: ' ' | upcase }}" data-title="{{post.about | upcase}}">{{post.about}}</div>
        </div>
      {% endif %}
      {% assign counter = counter | plus: 1 %}
	{% endunless %}
  {% endfor %}
</div>