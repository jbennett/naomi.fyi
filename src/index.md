---
layout: default
title: Posts
paginate:
  collection: posts
---

<div class="mx-auto max-w-prose space-y-12">
  {% for post in paginator.resources %}
    {% render 'post_body', post: post %}
  {% endfor %}
</div>

{% if paginator.total_pages > 1 %}
  <ul class="pagination">
    {% if paginator.previous_page %}
    <li>
      <a href="{{ paginator.previous_page_path }}">Previous Page</a>
    </li>
    {% endif %}
    {% if paginator.next_page %}
    <li>
      <a href="{{ paginator.next_page_path }}">Next Page</a>
    </li>
    {% endif %}
  </ul>
{% endif %}
