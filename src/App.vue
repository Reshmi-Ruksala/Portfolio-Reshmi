<script setup lang="ts">
import Navigation from './components/Navigation.vue'
import Hero from './components/Hero.vue'
import About from './components/About.vue'
import Skills from './components/Skills.vue'
import Projects from './components/Projects.vue'
import Contact from './components/Contact.vue'
</script>

<template>
  <div class="app">
    <Navigation />
    <Hero />
    <About />
    <Skills />
    <Projects />
    <Contact />
    <footer class="footer">
      <div class="footer-content">
        <div class="footer-section">
          <h3>Reshmi Ruksala</h3>
          <p>Full Stack Developer & Designer</p>
        </div>
        
        <div class="footer-section">
          <h4>Connect with me</h4>
          <div class="social-links">
            <a href="https://www.linkedin.com/in/reshmi-ruksala-44b847326/" target="_blank" class="social-link">
              <svg width="24" height="24" viewBox="0 0 24 24" fill="currentColor">
                <path d="M20.447 20.452h-3.554v-5.569c0-1.328-.027-3.037-1.852-3.037-1.853 0-2.136 1.445-2.136 2.939v5.667H9.351V9h3.414v1.561h.046c.477-.9 1.637-1.85 3.37-1.85 3.601 0 4.267 2.37 4.267 5.455v6.286zM5.337 7.433c-1.144 0-2.063-.926-2.063-2.065 0-1.138.92-2.063 2.063-2.063 1.14 0 2.064.925 2.064 2.063 0 1.139-.925 2.065-2.064 2.065zm1.782 13.019H3.555V9h3.564v11.452zM22.225 0H1.771C.792 0 0 .774 0 1.729v20.542C0 23.227.792 24 1.771 24h20.451C23.2 24 24 23.227 24 22.271V1.729C24 .774 23.2 0 22.222 0h.003z"/>
              </svg>
              <span>LinkedIn</span>
            </a>
            <a href="https://github.com/Reshmi-Ruksala" target="_blank" class="social-link">
              <svg width="24" height="24" viewBox="0 0 24 24" fill="currentColor">
                <path d="M12 0c-6.626 0-12 5.373-12 12 0 5.302 3.438 9.8 8.207 11.387.599.111.793-.261.793-.577v-2.234c-3.338.726-4.033-1.416-4.033-1.416-.546-1.387-1.333-1.756-1.333-1.756-1.089-.745.083-.729.083-.729 1.205.084 1.839 1.237 1.839 1.237 1.07 1.834 2.807 1.304 3.492.997.107-.775.418-1.305.762-1.604-2.665-.305-5.467-1.334-5.467-5.931 0-1.311.469-2.381 1.236-3.221-.124-.303-.535-1.524.117-3.176 0 0 1.008-.322 3.301 1.23.957-.266 1.983-.399 3.003-.404 1.02.005 2.047.138 3.006.404 2.291-1.552 3.297-1.23 3.297-1.23.653 1.653.242 2.874.118 3.176.77.84 1.235 1.911 1.235 3.221 0 4.609-2.807 5.624-5.479 5.921.43.372.823 1.102.823 2.222v3.293c0 .319.192.694.801.576 4.765-1.589 8.199-6.086 8.199-11.386 0-6.627-5.373-12-12-12z"/>
              </svg>
              <span>GitHub</span>
            </a>
            <a href="https://www.instagram.com/___resh____?igsh=OGZjZGpqc3dwbXd2&utm_source=qr" target="_blank" class="social-link">
              <svg width="24" height="24" viewBox="0 0 24 24" fill="currentColor">
                <path d="M12 2.163c3.204 0 3.584.012 4.85.07 3.252.148 4.771 1.691 4.919 4.919.058 1.265.069 1.645.069 4.849 0 3.205-.012 3.584-.069 4.849-.149 3.225-1.664 4.771-4.919 4.919-1.266.058-1.644.07-4.85.07-3.204 0-3.584-.012-4.849-.07-3.26-.149-4.771-1.699-4.919-4.92-.058-1.265-.07-1.644-.07-4.849 0-3.204.013-3.583.07-4.849.149-3.227 1.664-4.771 4.919-4.919 1.266-.057 1.645-.069 4.849-.069zm0-2.163c-3.259 0-3.667.014-4.947.072-4.358.2-6.78 2.618-6.98 6.98-.059 1.281-.073 1.689-.073 4.948 0 3.259.014 3.668.072 4.948.2 4.358 2.618 6.78 6.98 6.98 1.281.058 1.689.072 4.948.072 3.259 0 3.668-.014 4.948-.072 4.354-.2 6.782-2.618 6.979-6.98.059-1.28.073-1.689.073-4.948 0-3.259-.014-3.667-.072-4.947-.196-4.354-2.617-6.78-6.979-6.98-1.281-.059-1.69-.073-4.949-.073zm0 5.838c-3.403 0-6.162 2.759-6.162 6.162s2.759 6.163 6.162 6.163 6.162-2.759 6.162-6.163c0-3.403-2.759-6.162-6.162-6.162zm0 10.162c-2.209 0-4-1.79-4-4 0-2.209 1.791-4 4-4s4 1.791 4 4c0 2.21-1.791 4-4 4zm6.406-11.845c-.796 0-1.441.645-1.441 1.44s.645 1.44 1.441 1.44c.795 0 1.439-.645 1.439-1.44s-.644-1.44-1.439-1.44z"/>
              </svg>
              <span>Instagram</span>
            </a>
          </div>
        </div>
        
        <div class="footer-section">
          <h4>Quick Links</h4>
          <div class="quick-links">
            <a href="#about">About</a>
            <a href="#skills">Skills</a>
            <a href="#projects">Projects</a>
            <a href="#contact">Contact</a>
          </div>
        </div>
      </div>
      
      <div class="footer-bottom">
        <p>&copy; {{ new Date().getFullYear() }} Reshmi Ruksala. All rights reserved.</p>
      </div>
    </footer>
  </div>
</template>

<style scoped>
/* --- FOOTER STYLES (CHARCOAL & CRIMSON) --- */

/* Color variables for clarity */
.app {
  --color-primary: #92140C; /* Deep Crimson Accent */
  --color-text-light: #FFF8F0; /* Off-White/Cream Text */
  --color-bg-deep: #1E1E24; /* Deep Charcoal Background */
  --color-bg-dark: #2A2A35; /* Slightly lighter charcoal for contrast/gradients */
  --color-text-muted: #b3a093; /* Muted brown-gray for subtle text */
  position: relative;
  width: 100%;
  overflow-x: hidden;
}

.footer {
  /* Updated Background and Gradient */
  background: linear-gradient(135deg, var(--color-bg-deep) 0%, var(--color-bg-dark) 50%, var(--color-bg-deep) 100%);
  padding: 3rem 2rem 1.5rem;
  color: var(--color-text-light); /* Off-White Text */
  /* Updated Border Color */
  border-top: 1px solid rgba(146, 20, 12, 0.4); 
  box-shadow: 0 -5px 20px rgba(0, 0, 0, 0.3);
  width: 100%;
  box-sizing: border-box;
  overflow-x: hidden;
}

.footer-content {
  max-width: 1200px;
  margin: 0 auto;
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
  gap: 2rem;
  margin-bottom: 2rem;
}

.footer-section h3 {
  /* Updated Main Title Color */
  color: var(--color-primary); 
  margin-bottom: 0.5rem;
  font-size: 1.5rem;
}

.footer-section h4 {
  /* Updated Secondary Heading Color (Muted) */
  color: var(--color-text-muted); 
  margin-bottom: 1rem;
  font-size: 1.1rem;
  position: relative;
  padding-bottom: 0.5rem;
}

.footer-section h4::after {
  content: '';
  position: absolute;
  left: 0;
  bottom: 0;
  width: 40px;
  height: 2px;
  /* Updated Accent Line Color */
  background: var(--color-primary); 
}

.footer-section p {
  margin: 0.5rem 0;
  line-height: 1.6;
}

.social-links {
  display: flex;
  flex-direction: column;
  gap: 0.8rem;
}

.social-link {
  display: flex;
  align-items: center;
  gap: 0.8rem;
  color: var(--color-text-light);
  text-decoration: none;
  transition: all 0.3s ease;
  padding: 0.5rem 0.8rem;
  border-radius: 4px;
}

.social-link:hover {
  /* Updated Social Link Hover Color and Background */
  color: var(--color-primary); 
  background: rgba(146, 20, 12, 0.1); 
  transform: translateX(5px);
}

.social-link svg {
  flex-shrink: 0;
}

.quick-links {
  display: flex;
  flex-direction: column;
  gap: 0.8rem;
}

.quick-links a {
  color: var(--color-text-light);
  text-decoration: none;
  transition: all 0.3s ease;
  padding: 0.3rem 0;
}

.quick-links a:hover {
  /* Updated Quick Link Hover Color */
  color: var(--color-primary); 
  transform: translateX(5px);
}

.footer-bottom {
  max-width: 1200px;
  margin: 0 auto;
  padding-top: 1.5rem;
  /* Updated Border Color */
  border-top: 1px solid rgba(146, 20, 12, 0.2); 
  text-align: center;
  /* Updated Copyright Text Color */
  color: var(--color-text-muted); 
}

.footer-bottom p {
  margin: 0;
  font-size: 0.9rem;
}

/* Responsive adjustments */
@media (max-width: 768px) {
  .footer-content {
    grid-template-columns: 1fr;
    text-align: center;
  }
  
  .footer-section h4::after {
    left: 50%;
    transform: translateX(-50%);
  }
  
  .social-links, .quick-links {
    align-items: center;
  }
}
</style>