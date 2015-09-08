---
layout: page
title: Post by Category
permalink: /categoryview/
active: archivebycategory
sitemap: false
---
{% assign tags = site.categories | sort %}
{% assign sorted_posts = site.posts | sort: 'title' %}
<div>
{% for tag in tags %}
    <a class="category" href="#{{ tag | first | slugify }}">
            {{ tag[0] | replace:'-', ' ' }}({{ tag | last | size }})
    </a> &nbsp;
{% endfor %}
</div>
<p>&nbsp;</p>
<div id="index">

{% for tag in tags %}
<a name="{{ tag[0] | slugify }}"></a><h2>{{ tag[0] | replace:'-', ' ' }} <i class="badge">{{ tag | last | size }}</i> </h2>

{% for post in sorted_posts %}
{%if post.categories contains tag[0]%}

  <h3><a href="{{ site.url }}{{ post.url }}" title="{{ post.title }}">{{ post.title }} <p class="date">{{ post.date |  date: "%B %e, %Y" }}</p></a></h3>
   <p>{{ post.excerpt | strip_html | truncate: 160 }}</p>

{%endif%}
{% endfor %}

{% endfor %}
</div>

