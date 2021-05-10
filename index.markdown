---
layout: default
title: Home
---

<!-- Global site tag (gtag.js) - Google Analytics -->
<script async src="https://www.googletagmanager.com/gtag/js?id=UA-45385956-1">
</script>
<script>
  window.dataLayer = window.dataLayer || [];
    function gtag(){dataLayer.push(arguments);}
      gtag('js', new Date());
  gtag('config', 'UA-45385956-1');
  </script>

# Updates
* <b>2021-5-9:</b> [Second post](https://yc5-yc.github.io/2021/05/09/k-theory-ii.html) of the series is coming out!
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

---

# See Also

* [Andy Yuanning Zhang](https://math.wikinana.org/andy/start)
* [K-theory Blog](https://antieau.github.io/blog.html)
* [Sanath Devalapurkar](https://sanathdevalapurkar.github.io/blog/)

