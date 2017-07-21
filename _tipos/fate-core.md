---
layout: page
show_meta: false
subheadline: "Fate Core"
title: "Meus Materiais de Fate Core!"
teaser: "Esses são alguns materiais de Fate Core que tenho aqui nos meus cacarecos. Fique a vontade para se Servir"
header:
    image_fullwidth: FundoBlog.png
permalink: "/fate-core/"
---
<ul>
    {% for post in site.tags.Fate-Core %}
    <li><a href="{{ site.url }}{{ post.url }}">{{ post.title | markdownify | remove: '<p>' | remove: '</p>' }}</a></li>
    {% endfor %}
</ul>

