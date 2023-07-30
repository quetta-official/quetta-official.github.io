---
title: "프로그래밍 언어"
layout: archive
permalink: categories/["programming language"]
author_profile: true
sidebar_main: true
---

{% assign posts = site.categories.["Programming language"] %}
{% for post in posts %} {% include archive-single2.html type=page.entries_layout %} {% endfor %}
