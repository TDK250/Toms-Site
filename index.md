---
layout: default
title: Home
---

<div class="hero">
  <h1>Hello, I'm Tom Kerr</h1>
  <p>University of Victoria Commerce graduate working as a Quality Assurance Specialist in government services, with experience in leadership, board governance, and supporting vulnerable populations.</p>
</div>

<section class="content-section">
  <div class="section-grid">
    
    <div class="card">
      <h3>🏛️ Government & Public Service</h3>
      <p>Currently working as a QA Specialist at the Public Guardian and Trustee of BC, implementing quality assurance processes and collaborating with teams serving clients under 19.</p>
      <p><a href="/professional">View my professional background →</a></p>
    </div>

    <div class="card">
      <h3>✍️ Writing & Insights</h3>
      <p>Sharing thoughts on government technology, quality assurance practices, board governance, and lessons learned from diverse roles across public service and non-profit sectors.</p>
      <p><a href="/blog">Read my latest posts →</a></p>
    </div>

    <div class="card">
      <h3>🚀 Projects & Experience</h3>
      <p>From managing an $87,000 fundraising event to increasing social media engagement by 186%, showcasing work that spans QA, governance, marketing, and project management.</p>
      <p><a href="/projects">Explore my projects →</a></p>
    </div>

  </div>
</section>

<section class="content-section">
  <h2>About My Work</h2>
  <p>I'm a University of Victoria Commerce and Entrepreneurship graduate working at the intersection of quality assurance, government services, and organizational leadership. My current role involves ensuring quality processes for vulnerable populations, while my background spans board governance, event management, consulting, and digital marketing.</p>
  
  <p>From serving as Vice President of a community centre board to managing student consultants, from coordinating major fundraising events to implementing QA processes in government - I've learned that effective leadership and quality processes are essential whether you're serving brain injury survivors, university students, or government clients.</p>
  
  <p>This site documents insights from these diverse experiences, projects that showcase different skills, and thoughts on how we can build better systems and processes that truly serve people.</p>
</section>

<section class="content-section">
  <h2>Recent Highlights</h2>
  <div class="section-grid">
    
    <div class="card">
      <h3>Current Role</h3>
      <h4>Quality Assurance Specialist</h4>
      <p class="text-muted">Public Guardian and Trustee of BC • January 2025 - Present</p>
      <p>Implementing QA processes across Child and Youth Services division, reviewing reports of trauma, and ensuring quality service for clients under 19.</p>
    </div>
    
    <div class="card">
      <h3>Leadership Experience</h3>
      <h4>Board Vice President & Elected Senator</h4>
      <p class="text-muted">James Bay Community Centre & UVic Senate</p>
      <p>Three years of board governance experience, including executive leadership, strategic planning, and representing student interests at the university level.</p>
    </div>

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

    <div class="card">
      <h3>Featured Achievement</h3>
      <h4>Toss the Boss Event Success</h4>
      <p class="text-muted">Victoria Brain Injury Society • 2021</p>
      <p>Project managed the first annual event, raising $87,000 for brain injury survivors with 250+ attendees from 29 companies and 9 sponsors.</p>
    </div>

  </div>
</section>