---
layout: default
title: Home
---

<section class="hero-section">
  <div class="hero-content">
    <img src="{{ site.baseurl }}/assets/images/PXL_20241224_214716982.NIGHT.jpg" 
         alt="Profile Picture" 
         class="profile-image">
    <div class="hero-text">
      <h2>About Me</h2>
      <p>I'm a business professional working in organizations supporting vulnerable people. Currently, I help ensure children in government care receive quality legal and trust services as the Quality Assurance Specialist with the Public Guardian and Trustee.</p>
      
      <p>Previously, I've been a board VP for a community centre, managed fundraising events that brought in $87k for brain injury survivors, helped transform an iconic historic site, and served on my university's Senate.</p>
      
      <p>When I'm not working, I love rock climbing, writing, and messing with new technology. Check out my blog to learn more about what interest me!</p>
    </div>
  </div>
</section>

<section class="interests-section">
  <h3>What I'm Passionate About</h3>
  <div class="interests-container">
    <div class="interests-scroll">
      
      <div class="interest-card vulnerable">
        <span class="interest-icon">🤝</span>
        <div class="interest-title">Supporting Vulnerable Populations</div>
        <div class="interest-desc">I've dedicated my career to supporting vulnerable individuals through difficult times.</div>
      </div>

      <div class="interest-card governance">
        <span class="interest-icon">⚖️</span>
        <div class="interest-title">Effective Governance</div>
        <div class="interest-desc">I believe good leadership and governance are key to the success of any organisation.</div>
      </div>

      <div class="interest-card technology">
        <span class="interest-icon">💻</span>
        <div class="interest-title">Technology for Good</div>
        <div class="interest-desc">I believe bleeding edge technology can respect user rights. Open, secure, privacy-respecting tech is the way forward.</div>
      </div>

      <div class="interest-card cultural">
        <span class="interest-icon">🌍</span>
        <div class="interest-title">Cultural Literacy</div>
        <div class="interest-desc">I believe exploring different cultures is important to gain perspective, connections, and new ideas.</div>
      </div>

      <div class="interest-card financial">
        <span class="interest-icon">💰</span>
        <div class="interest-title">Financial Management</div>
        <div class="interest-desc">From personal to organizational, I believe competent financial management makes everything else easier.</div>
      </div>

      <div class="interest-card wellness">
        <span class="interest-icon">🏔️</span>
        <div class="interest-title">Health and Wellness</div>
        <div class="interest-desc">Whether rock climbing or getting enough sleep, staying healthy helps us help others.</div>
      </div>

    </div>
    <div class="scroll-hint">← Scroll to explore my interests →</div>
  </div>
</section>

<div id="vibe-banner" style="background: #222; color: #fff; text-align: center; padding: 1em; cursor: pointer; font-size: 1.2em; margin-bottom: 2rem; border-radius: 8px; box-shadow: 0 2px 8px rgba(0,0,0,0.08);">
  this website was vibe-coded
</div>

<section class="highlights-section">
  <h2>Recent Highlights</h2>
  <div class="highlights-grid">

    <div class="highlight-card">
      <h3>Latest Blog Post</h3>
      {% assign latest_post = site.posts.first %}
      {% if latest_post %}
        <h4><a href="{{ latest_post.url }}">{{ latest_post.title }}</a></h4>
        <p class="highlight-date">{{ latest_post.date | date: "%B %d, %Y" }}</p>
        <p>{{ latest_post.excerpt | strip_html | truncatewords: 25 }}</p>
      {% else %}
        <p class="coming-soon-text">Coming soon: insights on government QA, board governance, and lessons learned from diverse leadership roles.</p>
      {% endif %}
    </div>

    <div class="highlight-card">
      <h3>Current Role</h3>
      <h4>Quality Assurance Specialist</h4>
      <p class="highlight-date">Public Guardian and Trustee of BC</p>
      <p>Ensuring quality services for vulnerable youth and identifying opportunities for legal intervention and victim services.</p>
    </div>

  </div>
</section>

<style>
/* Home Page Styles */
.hero-section {
  margin-bottom: 3rem;
}

.hero-content {
  display: flex;
  align-items: center;
  gap: 2rem;
  flex-wrap: wrap;
}

.profile-image {
  width: 200px;
  height: 200px;
  border-radius: 50%;
  object-fit: cover;
  border: 4px solid var(--border);
  transition: transform 0.3s ease, box-shadow 0.3s ease;
  flex-shrink: 0;
}

.profile-image:hover {
  box-shadow: 0 8px 25px var(--shadow-hover);
}
.hero-text {
  flex: 1;
  min-width: 300px;
}

.hero-text h2 {
  color: var(--text-primary);
  margin-bottom: 1rem;
}

.hero-text p {
  color: var(--text-primary);
  line-height: 1.6;
  margin-bottom: 1rem;
}

/* Interests Section */
.interests-section {
  margin: 3rem 0;
}

.interests-section h3 {
  color: var(--text-primary);
  margin-bottom: 1.5rem;
  text-align: center;
}

.interests-container {
  margin: 2rem 0;
}

.interests-scroll {
  display: flex;
  overflow-x: auto;
  gap: 1rem;
  padding: 1rem 0;
  scroll-behavior: smooth;
  -webkit-overflow-scrolling: touch;
}

.interests-scroll::-webkit-scrollbar {
  height: 6px;
}

.interests-scroll::-webkit-scrollbar-track {
  background: var(--bg-secondary);
  border-radius: 3px;
}

.interests-scroll::-webkit-scrollbar-thumb {
  background: var(--accent);
  border-radius: 3px;
}

.interests-scroll::-webkit-scrollbar-thumb:hover {
  background: var(--accent-hover);
}

.interest-card {
  width: 200px;
  height: 200px;
  color: white;
  padding: 1.25rem;
  border-radius: 12px;
  text-align: center;
  transition: transform 0.3s ease, box-shadow 0.3s ease;
  cursor: pointer;
  flex-shrink: 0;
  display: flex;
  flex-direction: column;
  justify-content: center;
  word-wrap: break-word;
  overflow-wrap: break-word;
}

.interest-card:hover {
  transform: translateY(-5px);
  box-shadow: 0 10px 25px rgba(0,0,0,0.2);
}

.interest-card.vulnerable {
  background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
}

.interest-card.governance {
  background: linear-gradient(135deg, #f093fb 0%, #f5576c 100%);
}

.interest-card.technology {
  background: linear-gradient(135deg, #4facfe 0%, #00f2fe 100%);
}

.interest-card.cultural {
  background: linear-gradient(135deg, #43e97b 0%, #38f9d7 100%);
}

.interest-card.financial {
  background: linear-gradient(135deg, #fa709a 0%, #fee140 100%);
}

.interest-card.wellness {
  background: linear-gradient(135deg, #a8edea 0%, #fed6e3 100%);
  color: #333;
}

.interest-icon {
  font-size: 1.8rem;
  margin-bottom: 0.5rem;
  display: block;
}

.interest-title {
  font-weight: bold;
  margin-bottom: 0.5rem;
  font-size: 0.85rem;
  line-height: 1.2;
}

.interest-desc {
  font-size: 0.75rem;
  opacity: 0.95;
  line-height: 1.3;
  overflow: hidden;
  text-overflow: ellipsis;
}

.scroll-hint {
  text-align: center;
  color: var(--text-secondary);
  font-size: 0.9rem;
  margin-top: 0.5rem;
}

.site-description {
  text-align: center;
  color: var(--text-secondary);
  font-size: 1.1rem;
  max-width: 700px;
  margin: 2rem auto 0;
  line-height: 1.6;
}

/* Highlights Section */
.highlights-section {
  margin: 3rem 0;
}

.highlights-section h2 {
  color: var(--text-primary);
  margin-bottom: 2rem;
  text-align: center;
}

.highlights-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  gap: 2rem;
}

.highlight-card {
  background: var(--bg-secondary);
  border: 1px solid var(--border);
  border-radius: 0.75rem;
  padding: 2rem;
  transition: transform 0.3s ease, box-shadow 0.3s ease;
}

.highlight-card:hover {
  transform: translateY(-4px);
  box-shadow: 0 8px 25px var(--shadow-hover);
}

.highlight-card h3 {
  color: var(--accent);
  margin-bottom: 1rem;
  font-size: 1.1rem;
}

.highlight-card h4 {
  color: var(--text-primary);
  margin-bottom: 0.5rem;
}

.highlight-card h4 a {
  color: var(--text-primary);
  text-decoration: none;
  transition: color 0.2s ease;
}

.highlight-card h4 a:hover {
  color: var(--accent);
}

.highlight-date {
  color: var(--text-secondary);
  font-size: 0.9rem;
  margin-bottom: 1rem !important;
  font-style: italic;
}

.highlight-card p {
  color: var(--text-secondary);
  line-height: 1.6;
  margin-bottom: 0;
}

.coming-soon-text {
  color: var(--text-secondary) !important;
  font-style: italic;
}

/* Mobile responsive */
@media (max-width: 768px) {
  .hero-content {
    flex-direction: column;
    text-align: center;
  }
  
  .profile-image {
    width: 150px;
    height: 150px;
  }
  
  .interest-card {
    width: 180px;
    height: 180px;
    padding: 1rem;
  }
  
  .interest-title {
    font-size: 0.8rem;
  }
  
  .interest-desc {
    font-size: 0.7rem;
  }
  
  .highlights-grid {
    grid-template-columns: 1fr;
    gap: 1rem;
  }
  
  .highlight-card {
    padding: 1.5rem;
  }
}

@media (max-width: 480px) {
  .interest-card {
    width: 160px;
    height: 160px;
    padding: 0.875rem;
  }
  
  .interest-title {
    font-size: 0.75rem;
  }
  
  .interest-desc {
    font-size: 0.65rem;
  }
}

/* Smooth animations */
.hero-section,
.interests-section,
.highlights-section {
  animation: fadeInUp 0.6s ease-out;
}

@keyframes fadeInUp {
  from {
    opacity: 0;
    transform: translateY(20px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}
</style>

<script>
// Add smooth scrolling behavior for the interests section
document.addEventListener('DOMContentLoaded', function() {
  const interestCards = document.querySelectorAll('.interest-card');
  
  interestCards.forEach(card => {
    card.addEventListener('click', function() {
      this.style.transform = 'scale(0.95) translateY(-5px)';
      setTimeout(() => {
        this.style.transform = '';
      }, 150);
    });
  });

  // Banner click handler
  var banner = document.getElementById('vibe-banner');
  if (banner) {
    banner.onclick = function() {
      alert("I don't want to pretend my programming skills are better than they are. Pay someone to make a website for you if you can afford it. Jekyll and Github pages is a great option for anyone looking to create a personal website for free. LLMs make this approach much easier, more economical and more customizable than using traditional website building platforms.");
    };
  }
});
</script>
