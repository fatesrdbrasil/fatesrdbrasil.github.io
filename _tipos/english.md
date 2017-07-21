---
layout: page
show_meta: false
subheadline: "Everything I did in English!"
title: "Everything I did in English!"
permalink: "/english/"
---

My texts and posts in English!

{% capture site_categories %}{% for post in site.posts %}{% if post.language != "en" %}{% continue %}{% else %}{% for categories in post.categories %}{{ categories | lstrip | rstrip }},{% endfor %}{% endif %}{% endfor %}{% endcapture %}

{% assign categories_words = site_categories | strip_newlines | strip | split:',' | sort %}
{% assign categoriess = categories_words[1] %}

{% for item in categories_words %}
    {% unless categories contains item %}
        {% capture categories %}{{ categories }}|{{ item }}{% endcapture %}
    {% endunless %}
{% endfor %}

{% assign categorieslist = categories | strip_newlines | strip | split:'|' | sort %}

<ul> 
{% for categories in categorieslist %}
   {% if categories == "" or categories == nil %}
   {% continue %}
   {% endif %}

   {% assign real_category = categories | capitalize %}
   
   {% if real_category == "Personagens" %}{% assign real_category = "Characters" %}{% endif %}
   
   <li><h3> {{ real_category  }} </h3></li>
   <ul>

   {% assign sorted_pages = (site.posts | sort: 'title') %}
   {% for post in sorted_pages %}
   {% if post.language != "en" %}{% continue %}{% endif %}
   {% if post.categories contains categories %}
   <li><a href="{{ post.url }}">{{ post.title | markdownify | remove: '<p>' | remove: '</p>' }} </a> </li>
   {% endif %}
   {% endfor %}
   </ul>
{% endfor %}
</ul>

