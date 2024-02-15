---
layout: page
permalink: /categories/
title: Categories
---


<div id="archives">
{% for category in site.categories %}
  <div class="archive-group">
    {% capture category_name %}{{ category | first }}{% endcapture %}
    <div id="#{{ category_name | slugize }}"></div>
    <p></p>

    <h2 class="category-head">{{ category_name }}</h2>
    <a name="{{ category_name | slugize }}"></a>
    <ul>
      {% for post in site.categories[category_name] %}
      <li><article class="archive-item">
        <emph><a href="{{ site.baseurl }}{{ post.url }}">{{post.title}} (<i>{{ post.date | date: "%-d %B %Y" }}</i>)</a></emph>
      </article></li>
    {% endfor %}
    </ul>
  </div>
{% endfor %}
</div>