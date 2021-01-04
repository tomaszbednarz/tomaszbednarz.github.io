---
layout: default
permalink: /blog/
title: "Blog"
---

<br />
<div class="row" data-masonry='{"percentPosition": true }'>
  {% for post in site.posts %}
  <div class="col-sm-6 col-lg-4 mb-4">
    <div class="card text-center">
    <div class="card-body">
      {% if post.image %}
      {% capture imagePath %}/assets/posts/{{ post.date | date: "%Y-%m-%d" }}-{{ post.title | slugify }}/{{ include.name }}{{ post.image }}{% endcapture %}
      <a href="{{ post.url }}">{% include image.html name=imagePath full_path="yes" %}</a>
      {% endif %}
          <h5 class="card-title"><a href="{{ post.url }}">{{ post.title }}</a></h5>
          {% if post.tags %}
            <h6>
            <span class="badge bg-dark">TAGS</span>
            {% assign tags = post.tags %}
            {% for tag in tags %}
              <span class="badge bg-secondary">
              {{ tag | upcase }}
              </span>
            {% endfor %}
            </h6>
          {% endif %}
    </div>
    </div>
  </div>
  {% endfor %}
</div>
<script async src="https://cdn.jsdelivr.net/npm/masonry-layout@4.2.2/dist/masonry.pkgd.min.js" integrity="sha384-GNFwBvfVxBkLMJpYMOABq3c+d3KnQxudP/mGPkzpZSTYykLBNsZEnG2D9G/X/+7D" crossorigin="anonymous"></script> 






