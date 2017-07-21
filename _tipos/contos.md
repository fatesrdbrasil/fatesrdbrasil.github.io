---
layout: page
show_meta: false
title: "Meus Contos"
permalink: "/contos/"
---

Meus contos que escrevi

<ul>
    {% for post in site.categories.contos %}
    <li><a href="{{ post.url }}">{{ post.title | markdownify | remove: '<p>' | remove: '</p>' }}</a></li>
    {% comment %}
    {{ post.content }}
    {% endcomment %}
    {% endfor %}
</ul>


<br/>

Stories I've written (in English)

<ul>
    {% for post in site.categories.stories %}
    <li><a href="{{ post.url }}">{{ post.title | markdownify | remove: '<p>' | remove: '</p>' }}</a></li>
    {% comment %}
    {{ post.content }}
    {% endcomment %}
    {% endfor %}
</ul>
