---
layout: page
title: Tags
permalink: /tags/
---

{% assign sorted_tags = site.tags | sort %}
{% for tag in sorted_tags %}
  {% assign tag_name = tag[0] %}
  {% assign tag_posts = tag[1] %}
  <div id="{{ tag_name | slugify }}" style="margin-bottom:32px;">
    <div style="font-family:'Courier New',monospace;font-size:12px;letter-spacing:.16em;text-transform:uppercase;color:#d97757;margin-bottom:8px;">{{ tag_name }} ({{ tag_posts.size }})</div>
    <ul style="list-style:none;">
      {% for post in tag_posts %}
        <li style="padding:4px 0;">
          <span style="font-family:'Courier New',monospace;font-size:11px;color:#888;margin-right:8px;">{{ post.date | date: "%d/%m/%Y" }}</span>
          <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
        </li>
      {% endfor %}
    </ul>
  </div>
{% endfor %}
