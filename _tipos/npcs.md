---
layout: page
show_meta: false
title: "NPCs exemplos"
permalink: "/NPCs/"
---

    
Alguns NPCs exemplos que eu criei

{% assign those_posts = site.categories.npcs  | where: "language", "br" %}

{% capture site_tags %}
{% for post in those_posts %}
{% for tag in post.tags %}
{{ tag | lstrip | rstrip }}{% unless tag == "" %},{% endunless %}
{% endfor %}
{% endfor %}
{% endcapture %}


<!-- `tag_words` is a sorted array of the tag names. -->
{% assign tag_words = site_tags | strip_newlines | strip | split:',' | sort %}
{% assign tags = tag_words[1] %}


{% for item in tag_words %}
    {% unless tags contains item  %}
        {% capture tags %}{{ tags }}|{{ item }}{% endcapture %}
    {% endunless %}
{% endfor %}

{% assign taglist = tags | strip_newlines | strip | split:'|' | sort %}

<ul> 
{% for tag in taglist %}
   {% if tag == "" or tag == nil %}
   {% continue %}
   {% endif %}
   <li><h3> {{ tag }} </h3></li>
   <ul>
   {% assign sorted_pages = those_posts | sort: 'title' %}
   {% for post in sorted_pages %}
   {% if post.tags contains tag %}
   <li><a href="{{ post.url }}">{{ post.title | markdownify | remove: '<p>' | remove: '</p>' }} </a> </li>
   {% endif %}
   {% endfor %}
   </ul>
{% endfor %}
</ul>


Some NPCs I did (in English)

{% assign those_posts = site.categories.npcs | where: "language", "en" %}

{% capture site_tags %}
    {% for post in  those_posts %}
{% for tag in post.tags %}
{{ tag | lstrip | rstrip }}{% unless tag == "" %},{% endunless %}
{% endfor %}
{% endfor %}
{% endcapture %}

<!-- `tag_words` is a sorted array of the tag names. -->
{% assign tag_words = site_tags | strip_newlines | strip | split:',' | sort %}
{% assign tags = tag_words[1] %}


{% for item in tag_words %}
    {% unless tags contains item  %}
        {% capture tags %}{{ tags }}|{{ item }}{% endcapture %}
    {% endunless %}
{% endfor %}

{% assign taglist = tags | strip_newlines | strip | split:'|' | sort %}

<ul> 
{% for tag in taglist %}
   {% if tag == "" or tag == nil %}
   {% continue %}
   {% endif %}
   <li><h3> {{ tag }} </h3></li>
   <ul>
   {% assign sorted_pages = (those_posts | sort: 'title') %}
   {% for post in sorted_pages %}
   {% if post.tags contains tag %}
   <li><a href="{{ post.url }}">{{ post.title | markdownify | remove: '<p>' | remove: '</p>' }} </a> </li>
   {% endif %}
   {% endfor %}
   </ul>
{% endfor %}
</ul>
