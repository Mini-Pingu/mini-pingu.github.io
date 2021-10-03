---
title: /tags
layout: page
---

<fieldset>
<legend>
tags
</legend>

{% for tag in site.tags %}

<div>
  <strong>{{ tag[0] }}</strong>
  {% for post in tag[1] %}
  {%- assign date_format = "%Y-%m-%d" -%}
  <p>- [ {{ post.date | date: date_format }} ] <a href="{{ post.url }}">{{ post.title }}</a> </p>
  {% endfor %}

</div>
{% endfor %}
</fieldset>
