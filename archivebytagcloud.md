---
layout: page
title: Post by Tag Cloud
permalink: /tagcloudview/
active: archivebytagcloud
sitemap: false
---


{% assign tags = site.categories | sort %}
{% for tag in tags %}
 <span class="site-tag">
    <a href="/tag/{{ tag | first | slugify }}/"
        style="font-size: {{ tag | last | size  |  times: 4 | plus: 80  }}%">
            {{ tag[0] | replace:'-', ' ' }} ({{ tag | last | size }})
    </a>
</span>
{% endfor %}


