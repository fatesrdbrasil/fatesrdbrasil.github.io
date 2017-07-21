---
layout: page
show_meta: false
title: "Meus Cenários"
permalink: "/cenarios/"
---

Alguns cenários que eu criei

<ul>
    {% for post in site.pages %}
    {% if post.categories contains 'cenarios' %}
    <li><a href="{{ post.url }}">{{ post.title | markdownify | remove: '<p>' | remove: '</p>' }}</a></li>
    {% endif %}
    {% endfor %}
    {% for post in site.tags.cenarios %}
    <li><a href="{{ post.url }}">{{ post.title | markdownify | remove: '<p>' | remove: '</p>' }}</a></li>
    {% endfor %}
</ul>
