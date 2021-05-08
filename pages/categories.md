---
title: /categories
layout: page
permalink: /categories
---

# Categories

<ul>
{% for category in site.categories %}
  <li><a name="{{ category | first }}">{{ category | first }}</a>
    <ul>
    {% for post in category.last %}
      <ol> => [<time datetime="{{ post.date | date_to_xmlschema }}" itemprop="datePublished">{{ post.date | date: "%Y-%m-%d" }}] <a href="{{ site.url }}{{ post.url }}">{{ post.title }}</a></time></ol>
    {% endfor %}
    </ul>

  </li>
  <br />
{% endfor %}
</ul>
