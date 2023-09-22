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
  <ul class="pagination my-8 flex flex-wrap justify-center gap-x-2 gap-y-2">
    {% if paginator.previous_page %}
      <li class="block">
        <a href="{{ paginator.previous_page_path }}" class="block px-4 py-2 border-2 hover:border-fuchsia-400 hover:bg-fuchsia-200">Previous Page</a>
      </li>
    {% endif %}

    {% for page in paginator.page_trail %}
      <li class="block">
        {% if page.num == paginator.page %}
          <a href="{{ page.path }}" class="block px-4 py-2 border-2 border-fuchsia-400">{{ page.num }}</a>
        {% else %}
          <a href="{{ page.path }}" class="block px-4 py-2 border-2 hover:border-fuchsia-400 hover:bg-fuchsia-200">{{ page.num }}</a>
        {% endif %}
      </li>
    {% endfor %}

    {% if paginator.next_page %}
    <li class="block">
      <a href="{{ paginator.next_page_path }}" class="block px-4 py-2 border-2 hover:border-fuchsia-400 hover:bg-fuchsia-200">Next Page</a>
    </li>
    {% endif %}
  </ul>
{% endif %}
