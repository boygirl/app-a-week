---
layout: page
title: App-a-Week
tagline: Every Week!
---
{% include JB/setup %}

<h2 class="foo">Latest Post</h2>
----
{% assign x = site.posts.first %}
<h3><a href="{{ x.url }}">{{ x.title }}</a></h3>
{{ x.content }}
----
<h2 class="foo">More</h2>
<ul class="posts">
{% for post in site.posts limit:10 %}
{% if forloop.index != 1 %}
<li><span>{{ post.date | date_to_string }}</span> &raquo; <a href="{{ post.url }}">{{ post.title }}</a></li>
{% endif %}
{% endfor %}
</ul>






