---
layout: default
title: Home
---

<section class="content-section">
  <h2>About Me</h2>
  <p>I work at the intersection of business functions and social purpose. My current role involves ensuring quality processes for vulnerable populations, while my background spans board governance, event management, consulting, and digital marketing.</p>
  
  <p>From serving as Vice President of a community centre board to managing student consultants, from coordinating major fundraising events to implementing QA processes in government - I've learned that effective leadership and quality processes are essential whether you're serving brain injury survivors, university students, or government clients.</p>
  
  <p>This site documents insights from these diverse experiences, projects that showcase different skills, and thoughts on how we can build better systems and processes that serve people in need.</p>
</section>

<section class="content-section">
  <h2>Recent Highlights</h2>
  <div class="section-grid">

    <div class="card">
      <h3>Latest Blog Post</h3>
      {% assign latest_post = site.posts.first %}
      {% if latest_post %}
        <h4><a href="{{ latest_post.url }}">{{ latest_post.title }}</a></h4>
        <p class="text-muted">{{ latest_post.date | date: "%B %d, %Y" }}</p>
        <p>{{ latest_post.excerpt | strip_html | truncatewords: 25 }}</p>
      {% else %}
        <p class="text-muted">Coming soon: insights on government QA, board governance, and lessons learned from diverse leadership roles.</p>
      {% endif %}
    </div>

  </div>
</section>
