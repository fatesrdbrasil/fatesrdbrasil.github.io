---
layout: page
show_meta: false
subheadline: "Fate"
title: "Meus Materiais de Fate!"
teaser: "Esses são alguns materiais de Fate que tenho aqui nos meus cacarecos. Fique a vontade para se Servir"
header:
    image_fullwidth: FundoBlog.png
permalink: "/fate/"
---
<ul>
    {% for post in site.tags.Fate %}
    <li><a href="{{ site.url }}{{ post.url }}">{{ post.title | markdownify | remove: '<p>' | remove: '</p>' }}</a></li>
    {% endfor %}
</ul>
