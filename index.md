---
layout: page
title: App-a-Week
tagline: Every Week!
---
{% include JB/setup %}

<h1 class="foo">Latest Post</h1>
----
{% assign x = site.posts.first %}
<h2><a href="{{ x.url }}">{{ x.title }}</a></h2>
{{ x.content }}
<h1 class="foo">More Posts</h1>
<ul class="posts">
{% for post in site.posts limit:10 %}
{% if forloop.index != 1 %}
<li><span>{{ post.date | date_to_string }}</span> &raquo; <a href="{{ post.url }}">{{ post.title }}</a></li>
{% endif %}
{% endfor %}
</ul>


<h1 class="foo">Collaborators</h1>
<div id="collaborators">
</div>
<script>
$(document).ready(function() {
  var url = 'https://api.github.com/repos/crabasa/seattlehacks/collaborators';
  $.getJSON(url + '?callback=?', null, function(response) {
    response.data.forEach(function(collab) {
      $('<a href="' + collab.url + '"><img src=' + collab.avatar_url + '"/></a>').appendTo('#collaborators');
    });
  });
});
</script>



