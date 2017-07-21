---
layout: page
show_meta: false
subheadline: "Fate Acerelado"
title: "Meus Materiais de Fate Acelerado!"
teaser: "Esses são alguns materiais de Fate Acelerado que tenho aqui nos meus cacarecos. Fique a vontade para se Servir"
header:
    image_fullwidth: FundoBlog.png
permalink: "/fae/"
---
<ul>
    {% for post in site.tags.FAE %}
    <li><a href="{{ site.url }}{{ post.url }}">{{ post.title | markdownify | remove: '<p>' | remove: '</p>' }}</a></li>
    {% endfor %}
</ul>
