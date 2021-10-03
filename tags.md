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
  <strong>{{ tag[0] }}</strong><br/>
  {% for post in tag[1] %}
  {%- assign date_format = "%Y-%m-%d" -%}
  - [ {{ post.date | date: date_format }} ] <a href="{{ post.url }}">{{ post.title }}</a><br />
  {% endfor %}

</div><br/>
{% endfor %}
</fieldset>
