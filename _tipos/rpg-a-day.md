---
layout: page
show_meta: false
subheadline: "RPG-a-Day"
title: "As respostas minhas para o RPG-A-Day!"
header:
    image_fullwidth: FundoBlog.png
permalink: "/rpg-a-day/"
---
<ul>
      {% assign pages_list = site.rpg-a-day %}
      {% for node in pages_list %}
        {% if node.title != null %}
          {% if node.layout == "page" %}
            <li><a class="sidebar-nav-item{% if page.url == node.url %} active{% endif %}" href="{{ node.url }}">{{ node.title }}</a>
          {% endif %}
        {% endif %}
      {% endfor %}
