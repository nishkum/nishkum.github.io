---
layout: archive
title: ""
permalink: /publications/
author_profile: true
---

{% if author.googlescholar %}
  You can also find my articles on <u><a href="{{author.googlescholar}}">my Google Scholar profile</a>.</u>
{% endif %}

{% include base_path %}

# Publications
<!-- *<sup><span style="font-size:4mm;">&dagger;</span></sup>Author names alphabetic* -->
{% for post in site.publications reversed %}
  {% include archive-single.html %}
{% endfor %}

# Manuscripts
<!-- *<sup><span style="font-size:4mm;">&dagger;</span></sup>Author names alphabetic* -->
{% for post in site.manuscripts reversed %}
  {% include archive-single.html %}
{% endfor %}
