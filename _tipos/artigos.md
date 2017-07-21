---
layout: page
show_meta: false
subheadline: "Artigos"
title: "Meus Artigos e reviews!"
permalink: "/artigos/"
---

Artigos que escrevi ou traduzi
        
<ul>
    {% for post in site.tags.Artigos | sort: 'date' %}
    <li><a href="{{ post.url }}">{{ post.title | markdownify | remove: '<p>' | remove: '</p>' }}</a></li>
    {% endfor %}
</ul>

Reviews que escrevi

<ul>
    <li><h3>Em Português</h3>
        <ul>
             {% for post in site.categories.reviews | sort: 'date' %}
                 {% if post.language == "br" %}
                 <li><a href="{{ post.url }}">{{ post.title | markdownify | remove: '<p>' | remove: '</p>' }}</a></li>
                 {% endif %}
             {% endfor %}
        </ul>
    </li>
    <li><h3>Em Inglês</h3>
        <ul>
             {% for post in site.categories.reviews | sort: 'date' %}
                 {% if post.language == "en" %}
                 <li><a href="{{ post.url }}">{{ post.title | markdownify | remove: '<p>' | remove: '</p>' }}</a></li>
                 {% endif %}
             {% endfor %}
        </ul>
    </li>
</ul>

Relatos de Jogo

{% assign reports_br = site.categories.game-report | where: 'language','br' %}

{% assign reports_en = site.categories.game-report | where: 'language','en' %}

<ul>
    <li><h3>Em Português</h3>
        <ul>
             {% for post in reports_br  | sort: 'date' %}
                 <li><a href="{{ post.url }}">{{ post.title | markdownify | remove: '<p>' | remove: '</p>' }}</a></li>
             {% endfor %}
        </ul>
    </li>
    <li><h3>Em Inglês</h3>
        <ul>
             {% for post in reports_en | sort: 'date' %}
                 <li><a href="{{ post.url }}">{{ post.title | markdownify | remove: '<p>' | remove: '</p>' }}</a></li>
             {% endfor %}
        </ul>
    </li>
</ul>
