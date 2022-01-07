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

{% for writers in site.data.LP_writers %}
- The {{ LP_writer.name }} is a {{ LP_writer.title }} writer.
{% endfor %}

## Writers from Sao Paulo

{% for writer in site.data.LP_writers %}
{% if LP_writers.location == "Sao Paulo" %}- <strong style="color: {{ LP_writer.color }};">{{ LP_writer.name }}</strong>
{% else %}- <Rio de Janeiro>{{ LP_writer.name }}</Rio de Janeiro>
{% endif %}
{% endfor %}

## Writers from Rio de Janeiro

{% assign Rio de Janeiro_LP_writers = site.data.LP_writers | where: "location", "Rio de Janeiro" %}
{% for writer in Rio de Janeiro_LP_writers %}
- {{ LP_writer.name | upcase }}
{% endfor %}
