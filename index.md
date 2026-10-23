---
layout: default
title: Home
---

<section class="hero">
  <p class="eyebrow">Welcome</p>
  <h1>Make space for the life you want.</h1>
  <p class="intro">A gentle, practical place to pause, get clear, and take your next step with confidence.</p>
  <a class="button" href="{{ '/about/' | relative_url }}">Start here</a>
</section>

<section class="welcome">
  <h2>Progress does not have to be perfect.</h2>
  <p>Life coaching can help you notice what matters, understand what is getting in the way, and turn good intentions into manageable action.</p>
</section>


<section class="posts">
  <p class="eyebrow">From the journal</p>
  <h2>Reflections and practical encouragement</h2>
  <div class="post-list">
    {% for post in site.posts %}
      <article class="post-card">
        <p class="post-meta">{{ post.date | date: "%B %-d, %Y" }}</p>
        <h3><a href="{{ post.url | relative_url }}">{{ post.title }}</a></h3>
        <p>{{ post.excerpt | strip_html | truncate: 180 }}</p>
        <a href="{{ post.url | relative_url }}">Read the post →</a>
      </article>
    {% endfor %}
  </div>
</section>
