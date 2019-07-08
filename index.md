---
layout: default
title: Cornell GIS Cookbook (index)
permalink: /gis-cookbook
---

{% for page in site.pages %}
<p><a href="{{page.id}}">{{page.title}}</a></p>
{% endfor %}
