---
layout: dark
title: About
example: This is an example value.
---


This page describes the amazing {{ site.title }} by {{ site.author.name }}.
{{ page.example }}

{% include flupp.html %}

## This is my about page.

One this page you will learn more about my blog project and why it's important to do blogging.

- Share research
- Create an archive
- Engage in the public sphere

## List of LP Writers

{% for lpwriters in site.data.lpwriters %}
- {{ lpwriters.name }} wrote the book {{ lpwriters.title }} .
{% endfor %}

## Writers from Sao Paulo

The writers in bold are from São Paulo:
{% for lpwriters in site.data.lpwriters %}
{% if lpwriters.location == "Sao Paulo" %}- <strong style="color: {{ lpwriters.color }};">{{ lpwriters.name }}</strong>
{% else %} {{ lpwriters.name }}
{% endif %}
{% endfor %}

## Writers from Rio de Janeiro

{% assign RiodeJaneiro_lpwriters = site.data.lpwriters | where: "location", "Rio de Janeiro" %}
{% for lpwriter in RiodeJaneiro_lpwriters %}
- {{ lpwriters.title }}
{% endfor %}
