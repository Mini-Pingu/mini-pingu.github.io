---
title: /categories
layout: page
---

<fieldset>
<legend>
categories
</legend>

{% for category in site.categories %}

  <div>
    {% capture category_name %}{{ category | first }}{% endcapture %}
    <strong>{{ category_name }}</strong><br/>
    <a name="{{ category_name | slugize }}"></a>
    {% for post in site.categories[category_name] %}
    {%- assign date_format = "%Y-%m-%d" -%}
    - [ {{ post.date | date: date_format }} ] <a href="{{ site.baseurl }}{{ post.url }}">{{post.title}}</a><br/>
    {% endfor %}

  </div><br/>
{% endfor %}
</fieldset>
