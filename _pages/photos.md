---
layout: page
title: Photos
permalink: /photos/
description: A growing collection of my captures.
---

{% for photo in site.photos %}

{% if photo.redirect %}
<div class="photo">
    <div class="thumbnail">
        <a href="{{ photo.redirect }}" target="_blank">
        {% if photo.img %}
        <img class="thumbnail" src="{{ photo.img | prepend: site.baseurl | prepend: site.url }}"/>
        {% else %}
        <div class="thumbnail blankbox"></div>
        {% endif %}    
        <span>
            <h1>{{ photo.title }}</h1>
            <br/>
            <p>{{ photo.description }}</p>
        </span>
        </a>
    </div>
</div>
{% else %}

<div class="photo">
    <div class="thumbnail">
        <a href="{{ photo.url | prepend: site.baseurl | prepend: site.url }}">
        {% if photo.img %}
        <img class="thumbnail" src="{{ photo.img | prepend: site.baseurl | prepend: site.url }}"/>
        {% else %}
        <div class="thumbnail blankbox"></div>
        {% endif %}    
        <span>
            <h1>{{ photo.title }}</h1>
            <br/>
            <p>{{ photo.description }}</p>
        </span>
        </a>
    </div>
</div>

{% endif %}

{% endfor %}
