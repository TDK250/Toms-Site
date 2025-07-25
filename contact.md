---
layout: default
title: Contact
---

<div class="hero" style="margin-bottom: 3rem;">
  <h1>Get In Touch</h1>
  <p>I'm always interested in connecting with anyone who shares similar interests, whether it's for professional opportunities, collaboration, or just a friendly conversation.</p>
</div>

## Ways to Reach Me

<div class="contact-grid">
  
  <div class="contact-card">
    <div class="contact-icon">
      <i data-feather="mail"></i>
    </div>
    <h3>Email</h3>
    <p>For professional inquiries, collaboration opportunities, or just to say hello.</p>
    <a href="mailto:connect@tdkerr.ca" class="contact-link">connect@tdkerr.ca</a>
  </div>

  <div class="contact-card">
    <div class="contact-icon">
      <i data-feather="linkedin"></i>
    </div>
    <h3>LinkedIn</h3>
    <p>Connect with me for professional networking and career discussions.</p>
    <a href="https://ca.linkedin.com/in/tdkerr" target="_blank" rel="noopener" class="contact-link">View Profile</a>
  </div>

  <div class="contact-card">
    <div class="contact-icon">
      <i data-feather="github"></i>
    </div>
    <h3>GitHub</h3>
    <p>Check out my code, contribute to projects, or collaborate on open source work.</p>
    <a href="https://github.com/TDK250" target="_blank" rel="noopener" class="contact-link">View Projects</a>
  </div>

  <div class="contact-card">
    <div class="contact-icon">
      <i data-feather="rss"></i>
    </div>
    <h3>RSS Feed</h3>
    <p>Stay updated with my latest blog posts and thoughts.</p>
    <a href="{{ '/feed.xml' | relative_url }}" class="contact-link">Subscribe</a>
  </div>

</div>

---

<div class="availability-section">
  <div class="availability-content">
    <div class="availability-info">
      <h2><i data-feather="clock" style="width: 24px; height: 24px; margin-right: 0.5rem;"></i>Current Availability</h2>
      <p>I'm always happy to chat about shared interests, provide advice, or discuss potential collaboration opportunities.</p>
      
      <div class="availability-details">
        <div class="detail-item">
          <i data-feather="mail" class="detail-icon"></i>
          <div>
            <strong>Response Time</strong>
            <p>I typically respond to emails within 24-48 hours on weekdays.</p>
          </div>
        </div>
        
        <div class="detail-item">
          <i data-feather="video" class="detail-icon"></i>
          <div>
            <strong>Meeting Availability</strong>
            <p>Open to coffee chats, video calls, or professional networking meetings. I'm based in Victoria, BC, but happy to meet virtually.</p>
          </div>
        </div>
        
        <div class="detail-item">
          <i data-feather="map-pin" class="detail-icon"></i>
          <div>
            <strong>Location</strong>
            <p>Victoria, British Columbia, Canada (PST/PDT timezone)</p>
          </div>
        </div>
      </div>
    </div>
  </div>
</div>

<style>
/* Contact Page Specific Styles */
.contact-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
  gap: 1.5rem;
  margin: 2rem 0;
}

.contact-card {
  background: var(--bg-secondary);
  border: 1px solid var(--border);
  border-radius: 1rem;
  padding: 2rem;
  text-align: center;
  transition: all 0.3s ease;
  box-shadow: 0 2px 8px var(--shadow);
  position: relative;
  overflow: hidden;
}

.contact-card::before {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  height: 4px;
  background: linear-gradient(90deg, var(--accent), var(--accent-hover));
  transform: scaleX(0);
  transition: transform 0.3s ease;
}

.contact-card:hover::before {
  transform: scaleX(1);
}

.contact-card:hover {
  transform: translateY(-8px);
  box-shadow: 0 12px 24px var(--shadow-hover);
}

.contact-icon {
  width: 60px;
  height: 60px;
  background: linear-gradient(135deg, var(--accent), var(--accent-hover));
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  margin: 0 auto 1.5rem;
  transition: transform 0.3s ease;
}

.contact-card:hover .contact-icon {
  transform: scale(1.1) rotate(5deg);
}

.contact-icon i {
  width: 28px;
  height: 28px;
  color: white;
  stroke-width: 2;
}

.contact-card h3 {
  color: var(--text-primary);
  margin-bottom: 1rem;
  font-size: 1.25rem;
}

.contact-card p {
  color: var(--text-secondary);
  margin-bottom: 1.5rem;
  line-height: 1.6;
}

.contact-link {
  display: inline-flex;
  align-items: center;
  background: var(--accent);
  color: white;
  padding: 0.75rem 1.5rem;
  border-radius: 0.5rem;
  text-decoration: none;
  font-weight: 600;
  transition: all 0.2s ease;
  gap: 0.5rem;
}

.contact-link:hover {
  background: var(--accent-hover);
  transform: translateY(-2px);
  color: white;
}

.availability-section {
  background: var(--bg-secondary);
  border-radius: 1rem;
  padding: 2rem;
  margin: 3rem 0;
  border: 1px solid var(--border);
}

.availability-content h2 {
  display: flex;
  align-items: center;
  color: var(--text-primary);
  margin-bottom: 1rem;
}

.availability-details {
  display: grid;
  gap: 1.5rem;
  margin-top: 2rem;
}

.detail-item {
  display: flex;
  align-items: flex-start;
  gap: 1rem;
  padding: 1rem;
  background: var(--bg-primary);
  border-radius: 0.5rem;
  border: 1px solid var(--border);
}

.detail-icon {
  width: 20px;
  height: 20px;
  color: var(--accent);
  margin-top: 0.25rem;
  flex-shrink: 0;
}

.detail-item strong {
  display: block;
  color: var(--text-primary);
  margin-bottom: 0.25rem;
}

.detail-item p {
  margin: 0;
  color: var(--text-secondary);
  font-size: 0.9rem;
}

/* Responsive adjustments */
@media (max-width: 768px) {
  .contact-grid {
    grid-template-columns: 1fr;
    gap: 1rem;
  }
  
  .contact-card {
    padding: 1.5rem;
  }
  
  .availability-section {
    padding: 1.5rem;
  }
  
  .detail-item {
    flex-direction: column;
    text-align: center;
    gap: 0.5rem;
  }
  
  .detail-icon {
    align-self: center;
  }
}
</style>

<script>
// Initialize Feather icons when page loads
document.addEventListener('DOMContentLoaded', function() {
  if (typeof feather !== 'undefined') {
    feather.replace();
  }
});
</script>
