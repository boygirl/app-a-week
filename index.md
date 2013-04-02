---
layout: page
title: App-a-Week
tagline: Every Week!
---
{% include JB/setup %}




<h1 class="foo">Collaborators</h1>
<div id="collaborators">
</div>
<script>
$(document).ready(function() {
  var url = 'https://api.github.com/repos/leastridge/app-a-week/collaborators';
  $.getJSON(url + '?callback=?', null, function(response) {
    response.data.forEach(function(collab) {
      $('<a href="' + collab.url + '"><img src=' + collab.avatar_url + '"/></a>').appendTo('#collaborators');
    });
  });
});
</script>


