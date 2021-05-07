---
layout: default
title: Home
---

# Updates
* <b>2021-5-7:</b> New post! [What is algebraic K-theory?](https://yc5-yc.github.io/2021/05/07/k-theory-i.html)
* <b>2021-4-17:</b> Welcome to my new website!

---

# [About Me](/about)

---

# Blog Posts

<div class="home">



    {% assign posts = site.posts %}


  {%- if posts.size > 0 -%}
    <ul class="post-list">
      {%- assign date_format = site.minima.date_format | default: "%b %-d, %Y" -%}
      {%- for post in posts -%}
      <li>
        <span class="post-meta">{{ post.date | date: date_format }}</span>
        <h3>
          <a class="post-link" href="{{ post.url | relative_url }}">
            {{ post.title | escape }}
          </a>
        </h3>
        {%- if site.show_excerpts -%}
          {{ post.excerpt }}
        {%- endif -%}
      </li>
      {%- endfor -%}
    </ul>

    

  {%- endif -%}

</div>

<!-- https://q.uiver.app/?q=WzAsMyxbMCwwLCJYIl0sWzEsMCwiWSJdLFswLDEsIlciXSxbMCwxLCJmJyJdLFswLDIsImcnIiwyXV0= -->
<iframe class="quiver-embed" src="https://q.uiver.app/?q=WzAsMyxbMCwwLCJYIl0sWzEsMCwiWSJdLFswLDEsIlciXSxbMCwxLCJmJyJdLFswLDIsImcnIiwyXV0=&embed" width="304" height="304" style="border-radius: 8px; border: none;"></iframe>
