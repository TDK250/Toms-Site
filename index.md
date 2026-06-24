---
layout: default
title: Home
---

<section class="hero-section">
  <div class="hero-content">
    <div class="profile-coin-wrapper" id="profileCoinWrapper">
      <div class="profile-coin" id="profileCoin">
        <div class="profile-face profile-front">
          <img src="{{ site.baseurl }}/assets/images/Profpic.jpg" alt="Profile Picture" decoding="async" fetchpriority="high">
        </div>
        <div class="profile-face profile-back">
          <img src="{{ site.baseurl }}/assets/images/Profpic.jpg" alt="Profile Picture" decoding="async" fetchpriority="high">
        </div>
      </div>
    </div>
    <div class="hero-text">
      <h2>About Me</h2>
      <p>I'm a law student at Dalhousie University (JD Class of 2029) with a background in business operations, board governance, and public sector quality assurance. Most recently, I worked with the Public Guardian and Trustee of BC to ensure vulnerable youth in government care receive high-quality legal and trust services.</p>
      
      <p>Prior to law school, I served as a Board Vice President for a community centre, directed consulting projects, managed fundraising campaigns that raised $87k for brain injury survivors, and represented my peers on the University of Victoria Senate.</p>
      
      <p>Outside of law school, I'm passionate about rock climbing, writing, and leveraging technology for social good. Check out my blog to explore my latest thoughts and projects!</p>
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
      <h3>Current Focus</h3>
      <h4>JD Candidate (Class of 2029)</h4>
      <p class="highlight-date">Dalhousie University Schulich School of Law</p>
      <p>Building on my background in quality assurance and board governance to study law and advocate for vulnerable populations.</p>
    </div>

    <div class="highlight-card">
      <h3>Recent Project</h3>
      <h4><a href="https://tdk250.github.io/track-a-mole/" target="_blank">Track-A-Mole</a></h4>
      <p>Building a secure, local-first skin health monitoring app with interactive 3D mapping for a trustworthy user experience.</p>
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

.profile-coin-wrapper {
  perspective: 700px;
  flex-shrink: 0;
  width: 208px;
  height: 208px;
  cursor: grab;
  user-select: none;
}

.profile-coin-wrapper:active {
  cursor: grabbing;
}

.profile-coin {
  width: 208px;
  height: 208px;
  position: relative;
  transform-style: preserve-3d;
  border-radius: 50%;
  box-shadow: 0 6px 24px rgba(0,0,0,0.25);
  transition: box-shadow 0.2s ease;
  will-change: transform;
}

.profile-coin:hover {
  box-shadow: 0 10px 32px rgba(0,0,0,0.35);
}

.profile-face {
  position: absolute;
  inset: 0;
  border-radius: 50%;
  backface-visibility: hidden;
  -webkit-backface-visibility: hidden;
}

.profile-front {
  transform: translateZ(1px);
  overflow: hidden;
}

.profile-face img {
  width: 100%;
  height: 100%;
  object-fit: cover;
  border-radius: 50%;
  display: block;
  pointer-events: none;
}

.profile-back {
  transform: rotateY(180deg) translateZ(1px);
  overflow: hidden;
}

.profile-back img {
  transform: scaleX(-1);
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
  align-items: stretch;
  overflow-x: auto;
  gap: 1rem;
  padding: 1rem 0;
  scroll-behavior: smooth;
  -webkit-overflow-scrolling: touch;
  cursor: grab;
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
  min-height: 200px;
  height: auto;
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
  
  .profile-coin-wrapper,
  .profile-coin {
    width: 160px;
    height: 160px;
  }
  
  .interest-card {
    width: 180px;
    min-height: 180px;
    height: auto;
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
    min-height: 180px;
    height: auto;
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
document.addEventListener('DOMContentLoaded', function() {

  // Interest card click bounce
  const interestCards = document.querySelectorAll('.interest-card');
  interestCards.forEach(card => {
    card.addEventListener('click', function() {
      this.style.transform = 'scale(0.95) translateY(-5px)';
      setTimeout(() => { this.style.transform = ''; }, 150);
    });
  });

  // ── 3D coin drag easter egg ──────────────────────────────────────────
  const wrapper = document.getElementById('profileCoinWrapper');
  const coin    = document.getElementById('profileCoin');
  if (!wrapper || !coin) return;

  let rotY       = 0;
  let isDragging = false;
  let startX     = 0;
  let startRotY  = 0;
  let lastX      = 0;
  let lastT      = 0;
  let velocity   = 0;
  let rafId      = null;
  let dragDist   = 0;

  function applyRotation(deg) {
    rotY = deg;
    coin.style.transform = `rotateY(${deg}deg)`;
  }

  function startMomentum() {
    cancelAnimationFrame(rafId);
    (function loop() {
      if (Math.abs(velocity) < 0.08) { velocity = 0; return; }
      velocity *= 0.94;
      applyRotation(rotY + velocity);
      rafId = requestAnimationFrame(loop);
    })();
  }

  function onDragStart(clientX) {
    cancelAnimationFrame(rafId);
    isDragging = true;
    dragDist   = 0;
    startX     = clientX;
    startRotY  = rotY;
    lastX      = clientX;
    lastT      = Date.now();
    velocity   = 0;
  }

  function onDragMove(clientX) {
    if (!isDragging) return;
    const now = Date.now();
    const dx  = clientX - lastX;
    const dt  = Math.max(now - lastT, 1);
    velocity  = (dx / dt) * 14;   // scale to px-per-frame
    dragDist += Math.abs(clientX - lastX);
    lastX = clientX;
    lastT = now;
    applyRotation(startRotY + (clientX - startX) * 0.55);
  }

  function onDragEnd() {
    if (!isDragging) return;
    isDragging = false;
    wrapper.style.cursor = 'grab';
    // If barely moved, treat as click → random spin up to a reasonable limit
    if (dragDist < 6) {
      cancelAnimationFrame(rafId);
      const extraSpins = (Math.floor(Math.random() * 3) + 1) * 360; // 1 to 3 random spins (360, 720, or 1080 deg)
      const start = rotY;
      const end   = Math.floor(rotY / 360) * 360 + extraSpins;
      const totalSpin = end - start;
      const dur   = 1000 + (totalSpin - 360) * 1.2; // scale duration based on total rotation
      const t0    = performance.now();
      (function spin() {
        const p = Math.min((performance.now() - t0) / dur, 1);
        // ease-out cubic
        const ease = 1 - Math.pow(1 - p, 3);
        applyRotation(start + (end - start) * ease);
        if (p < 1) requestAnimationFrame(spin);
        else rotY = end % 360;
      })();
    } else {
      startMomentum();
    }
  }

  // Mouse
  wrapper.addEventListener('mousedown', e => {
    onDragStart(e.clientX);
    wrapper.style.cursor = 'grabbing';
    e.preventDefault();
  });
  document.addEventListener('mousemove', e => { if (isDragging) onDragMove(e.clientX); });
  document.addEventListener('mouseup',   ()  => onDragEnd());

  // Touch
  wrapper.addEventListener('touchstart', e => {
    onDragStart(e.touches[0].clientX);
  }, { passive: true });
  wrapper.addEventListener('touchmove', e => {
    onDragMove(e.touches[0].clientX);
  }, { passive: true });
  wrapper.addEventListener('touchend', () => onDragEnd());

  // Grab-scroll for interests carousel
  const interestsScroll = document.querySelector('.interests-scroll');
  if (interestsScroll) {
    let isDown = false;
    let startX = 0;
    let scrollLeft = 0;
    let isDragging = false;

    // touch/swipe for desktop only (mobile uses native scroll)
    let touchStartX = 0;
    let touchScrollLeft = 0;
    interestsScroll.addEventListener('touchstart', (e) => {
      if (window.innerWidth <= 768) return;
      touchStartX = e.touches[0].pageX;
      touchScrollLeft = interestsScroll.scrollLeft;
    });
    interestsScroll.addEventListener('touchmove', (e) => {
      if (window.innerWidth <= 768) return;
      if (!touchStartX) return;
      const x = e.touches[0].pageX;
      const walk = (touchStartX - x) * 1.5;
      interestsScroll.scrollLeft = touchScrollLeft + walk;
    });
    interestsScroll.addEventListener('touchend', () => {
      touchStartX = 0;
    });

    let scrollRafId = null;

    interestsScroll.addEventListener('mousedown', (e) => {
      if (e.button !== 0 || e.target.closest('a, button, input, select, textarea')) return;
      isDown = true;
      isDragging = false;
      startX = e.pageX - interestsScroll.offsetLeft;
      scrollLeft = interestsScroll.scrollLeft;
      interestsScroll.style.cursor = 'grabbing';
    });

    document.addEventListener('mousemove', (e) => {
      if (!isDown) return;
      const x = e.pageX - interestsScroll.offsetLeft;
      const walk = (x - startX) * 1.2;
      if (Math.abs(walk) > 5) {
        isDragging = true;
        e.preventDefault(); // Stop browser text selection/scrolling
        
        if (!scrollRafId) {
          scrollRafId = requestAnimationFrame(() => {
            interestsScroll.scrollLeft = scrollLeft - walk;
            scrollRafId = null;
          });
        }
        
        interestsScroll.style.cursor = 'grabbing';
        window.getSelection().removeAllRanges();
      }
    });

    document.addEventListener('mouseup', () => {
      if (isDown) {
        isDown = false;
        interestsScroll.style.cursor = '';
        if (scrollRafId) {
          cancelAnimationFrame(scrollRafId);
          scrollRafId = null;
        }
      }
    });

    interestsScroll.addEventListener('click', (e) => {
      if (isDragging) {
        e.preventDefault();
        e.stopPropagation();
        isDragging = false;
      }
    }, true);
  }

});
</script>
