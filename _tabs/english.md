---
title: English
icon: fas fa-language
order: 6
lang: en
permalink: /en/
---

**Building AI products — from the trenches.**

If you want to understand what really happens when you build an AI product — the choices, the mistakes, the hard parts no demo shows — you're in the right place. Here I write about what happens when you try to build one.

I'm Enrico, CTO & Head of AI at [Stories](https://stories-app.it), a startup building a conversational AI companion for older adults. The blog is written in Italian first; the posts most relevant outside Italy are translated here.

## Posts in English

{% assign en_posts = site.posts | where: 'lang', 'en' %}
{% if en_posts.size > 0 %}
<ul>
{% for post in en_posts %}
  <li>
    <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
    <span class="text-muted small"> — {{ post.date | date: '%B %-d, %Y' }}</span>
  </li>
{% endfor %}
</ul>
{% else %}
The first translations are on their way.
{% endif %}

## Stay in touch

You can follow the English posts through the [RSS feed](/en/feed.xml), or find me on [LinkedIn](https://www.linkedin.com/in/enricomautone) and [GitHub](https://github.com/enrico-mautone). The newsletter at the bottom of the page is in Italian.
