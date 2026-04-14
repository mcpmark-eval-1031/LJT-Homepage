---
layout: archive
title: "Archive Layout with Content"
permalink: /archive-layout-with-content/
---

{% include base_path %}

<p>This is an example of how to use the <code>archive</code> layout with additional page content. It's useful for creating a custom landing page for a collection.</p>

<div class="archive">
  <h1 class="page__title">Recent Posts</h1>
  {% for post in site.posts limit:5 %}
    {% include archive-single.html %}
  {% endfor %}
</div>
