---
layout: default
title: Home
---

<style>
.hero-section {
  display: flex;
  align-items: center;
  gap: 2rem;
  margin-bottom: 2rem;
  flex-wrap: wrap;
}

.profile-image {
  width: 200px;
  height: 200px;
  border-radius: 50%;
  object-fit: cover;
  border: 4px solid #e9ecef;
  transition: transform 0.3s ease, box-shadow 0.3s ease;
}

.profile-image:hover {
  transform: scale(1.05);
  box-shadow: 0 8px 25px rgba(0,0,0,0.15);
}

.hero-text {
  flex: 1;
  min-width: 300px;
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
  background: #f1f1f1;
  border-radius: 3px;
}

.interests-scroll::-webkit-scrollbar-thumb {
  background: #c1c1c1;
  border-radius: 3px;
}

.interests-scroll::-webkit-scrollbar-thumb:hover {
  background: #a8a8a8;
}

.interest-card {
  min-width: 180px;
  background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
  color: white;
  padding: 1.5rem;
  border-radius: 12px;
  text-align: center;
  transition: transform 0.3s ease, box-shadow 0.3s ease;
  cursor: pointer;
  flex-shrink: 0;
}

.interest-card:hover {
  transform: translateY(-5px);
  box-shadow: 0 10px 25px rgba(0,0,0,0.2);
}

.interest-card.governance {
  background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
}

.interest-card.consulting {
  background: linear-gradient(135deg, #f093fb 0%, #f5576c 100%);
}

.interest-card.digital {
  background: linear-gradient(135deg, #4facfe 0%, #00f2fe 100%);
}

.interest-card.qa {
  background: linear-gradient(135deg, #43e97b 0%, #38f9d7 100%);
}

.interest-card.community {
  background: linear-gradient(135deg, #fa709a 0%, #fee140 100%);
}

.interest-card.events {
  background: linear-gradient(135deg, #a8edea 0%, #fed6e3 100%);
  color: #333;
}

.interest-icon {
  font-size: 2rem;
  margin-bottom: 0.5rem;
  display: block;
}

.interest-title {
  font-weight: bold;
  margin-bottom: 0.5rem;
  font-size: 0.9rem;
}

.interest-desc {
  font-size: 0.8rem;
  opacity: 0.9;
  line-height: 1.3;
}

.scroll-hint {
  text-align: center;
  color: #6c757d;
  font-size: 0.9rem;
  margin-top: 0.5rem;
}

@media (max-width: 768px) {
  .hero-section {
    flex-direction: column;
    text-align: center;
  }
  
  .profile-image {
    width: 150px;
    height: 150px;
  }
  
  .interest-card {
    min-width: 160px;
  }
}

.fade-in {
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

<section class="content-section fade-in">
  <div class="hero-section">
    <img src="{{ site.baseurl }}/assets/images/PXL_20241224_214716982.NIGHT.jpg" 
         alt="Profile Picture" 
         class="profile-image">
    <div class="hero-text">
      <h2>Hi, I'm Tom.</h2>
      <p>I work at the intersection of business functions and social purpose. My current role involves ensuring quality processes for vulnerable populations, while my background spans board governance, event management, consulting, and digital marketing.</p>
      
      <p>From serving as Vice President of a community centre board to managing student consultants, from coordinating major fundraising events to implementing QA processes in government - I've learned that effective leadership and quality processes are essential whether you're serving brain injury survivors, university students, or government clients.</p>
    </div>
  </div>
</section>

<section class="content-section">
  <div class="interests-container">
    <h3>What I'm Passionate About</h3>
    <div class="interests-scroll">
      
      <div class="interest-card governance">
        <span class="interest-icon">⚖️</span>
        <div class="interest-title">Board Governance</div>
        <div class="interest-desc">Ensuring effective oversight and strategic direction for community organizations</div>
      </div>

      <div class="interest-card consulting">
        <span class="interest-icon">💡</span>
        <div class="interest-title">Strategic Consulting</div>
        <div class="interest-desc">Helping organizations solve complex problems through data-driven insights</div>
      </div>

      <div class="interest-card digital">
        <span class="interest-icon">📱</span>
        <div class="interest-title">Digital Marketing</div>
        <div class="interest-desc">Building meaningful connections between brands and their communities</div>
      </div>

      <div class="interest-card qa">
        <span class="interest-icon">🔍</span>
        <div class="interest-title">Quality Assurance</div>
        <div class="interest-desc">Creating systems that protect and serve vulnerable populations effectively</div>
      </div>

      <div class="interest-card community">
        <span class="interest-icon">🤝</span>
        <div class="interest-title">Community Impact</div>
        <div class="interest-desc">Supporting brain injury survivors and building stronger communities</div>
      </div>

      <div class="interest-card events">
        <span class="interest-icon">🎯</span>
        <div class="interest-title">Event Management</div>
        <div class="interest-desc">Orchestrating memorable experiences that bring people together for a cause</div>
      </div>

    </div>
    <div class="scroll-hint">← Scroll to explore my interests →</div>
  </div>

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

<script>
// Add smooth scrolling behavior for the interests section
document.addEventListener('DOMContentLoaded', function() {
  const interestCards = document.querySelectorAll('.interest-card');
  
  interestCards.forEach(card => {
    card.addEventListener('click', function() {
      this.style.transform = 'scale(0.95)';
      setTimeout(() => {
        this.style.transform = '';
      }, 150);
    });
  });
});
</script>
