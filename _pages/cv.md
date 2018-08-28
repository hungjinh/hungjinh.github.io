---
layout: archive
permalink: /cv/
author_profile: true
---

[Click to View My Curriculum Vitae [PDF]](http://hungjinh.github.io/files/cv_HH.pdf)

<!-- <embed src="http://hungjinh.github.io/files/cv_HH.pdf" width="650" height="1800" type='application/pdf'> -->

{% include base_path %}
{% include group-by-array collection=site.posts field="tags" %}

{% for tag in group_names %}
  {% assign posts = group_items[forloop.index0] %}
  <h2 id="{{ tag | slugify }}" class="archive__subtitle">{{ tag }}</h2>
  {% for post in posts %}
    {% include archive-single.html %}
  {% endfor %}
{% endfor %}