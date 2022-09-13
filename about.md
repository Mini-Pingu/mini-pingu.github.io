---
title: /about
layout: page
permalink: /about
---

<center><strong>Just a tech.</strong></center>

<center><div>
{% for entry in site.data.social-media %}
<a href="{{ entry.href }}/{{ entry.id }}" title="{{ entry.id }}" target="_blank">{{ entry.title }}</a>
{% endfor %}
</div></center>
