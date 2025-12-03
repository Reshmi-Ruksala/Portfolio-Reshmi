<template>
  <section id="home" class="hero">
    <div class="hero-background">
      <div class="accent-anchor-block"></div>
    </div>

    <div class="hero-content">
      
      <div class="hero-text-area">
        <div class="text-inner-wrap">
          <div class="greeting-container">
            <p class="greeting">Hello, I'm</p>
          </div>

          <h1 class="name">
            <span class="name-line">Reshmi</span>
            <span class="name-line last-name">Ruksala</span>
          </h1>

          <div class="title-container">
            <p class="title">Full Stack Developer</p>
            <div class="title-cursor"></div>
          </div>

          <div class="description-container">
            <p class="description">
              A dedicated <strong>full-stack developer</strong> with a strong focus on <strong>backend engineering</strong> and building scalable, high-performance systems. 
              With experience completing 6+ full-stack projects and working with international clients, I specialize in 
              crafting modern web applications, cloud-powered solutions, and clean user experiences using modern technologies.
            </p>
          </div>

          <div class="hero-buttons">
            <a href="#projects" class="btn btn-primary" @click.prevent="handleNavClick('#projects')">
              <span>View My Work</span>
              <svg width="20" height="20" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
                <path d="M7 17L17 7M17 7H7M17 7V17" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
              </svg>
            </a>
            <a href="#contact" class="btn btn-secondary" @click.prevent="handleNavClick('#contact')">
              <span>Get In Touch</span>
              <svg width="20" height="20" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
                <path d="M21 11.5C21.0034 12.8199 20.6951 14.1219 20.1 15.3C19.3944 16.7118 18.3098 17.8992 16.9674 18.7293C15.6251 19.5594 14.0782 19.9994 12.5 20C11.1801 20.0034 9.87812 19.6951 8.7 19.1L3 21L4.9 15.3C4.30493 14.1219 3.99656 12.8199 4 11.5C4.00061 9.92179 4.44061 8.37488 5.27072 7.03258C6.10083 5.69028 7.28825 4.6056 8.7 3.90003C9.87812 3.30496 11.1801 2.99659 12.5 3.00003H13C15.0843 3.11502 17.053 3.99479 18.5291 5.47089C20.0052 6.94699 20.885 8.91568 21 11V11.5Z" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
              </svg>
            </a>
          </div>
        </div>
      </div>

      <div class="hero-image-area">
        <div class="image-container">
          <div class="image-placeholder">
            <img :src="binadaPic" alt="Reshmi Ruksala Profile" class="profile-image" />
          </div>
          
          <div class="tech-badge badge-1">
            <span>.NET</span>
          </div>
          <div class="tech-badge badge-2">
            <span>Python</span>
          </div>
          <div class="tech-badge badge-3">
            <span>AWS</span>
          </div>
          <div class="tech-badge badge-4">
            <span>MERN</span>
          </div>
          
          <div class="image-glow"></div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup lang="ts">
import binadaPic from '../assets/binada.png'

const handleNavClick = (sectionId: string) => {
  const element = document.querySelector(sectionId)
  if (element) {
    const offset = 80
    const elementPosition = element.getBoundingClientRect().top + window.pageYOffset
    const offsetPosition = elementPosition - offset

    window.scrollTo({
      top: offsetPosition,
      behavior: 'smooth'
    })
  }
}
</script>

<style scoped>
/* --- COLOR VARIABLES --- */
.hero {
  --color-primary: #92140C; /* Deep Crimson Accent */
  --color-text-light: #FFF8F0; /* Off-White/Cream Text */
  --color-bg-deep: #1E1E24; /* Deep Charcoal Background */
  --color-bg-dark: #2A2A35; /* Slightly lighter charcoal for contrast/gradients */
  
  --accent-mid: var(--color-primary);
  --accent-dark: #6E100A; /* Darker Crimson */
  --bg-deep: var(--color-bg-deep);
  --bg-dark: var(--color-bg-dark);
  --text-muted: #b3a093; /* Muted brown-gray for subtle text */
  --text-soft: var(--color-text-light);

  min-height: 100vh;
  display: flex;
  align-items: center;
  justify-content: center;
  padding: 120px 0 2rem;
  background: linear-gradient(135deg, var(--bg-deep) 0%, var(--bg-dark) 100%);
  position: relative;
  width: 100%;
  box-sizing: border-box;
  overflow: hidden;
}

/* Background - Anchor Block */
.hero-background {
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  pointer-events: none;
}

.accent-anchor-block {
  position: absolute;
  top: 0;
  right: 0;
  width: 50%; 
  height: 100%;
  background-color: var(--color-bg-dark); 
  z-index: 0;
  clip-path: polygon(10% 0%, 100% 0%, 100% 100%, 0% 100%); 
  box-shadow: -15px 0 40px rgba(0, 0, 0, 0.5);
}

.hero-content {
  max-width: 1400px;
  width: 100%;
  margin: 0 auto;
  padding: 2rem;
  display: grid;
  grid-template-columns: 1.2fr 1fr;
  gap: 2rem;
  align-items: center;
  z-index: 10;
  position: relative;
}

/* Text Area */
.hero-text-area {
  padding-right: 2rem;
  animation: slideInLeft 1s ease;
}

.greeting {
  font-size: 1.2rem;
  color: var(--accent-mid);
  margin-bottom: 0.5rem;
  font-weight: 600;
  letter-spacing: 2px;
  text-transform: uppercase;
  animation: dropIn 0.6s ease-out 0.2s both;
}

.name {
  font-size: clamp(3.5rem, 8vw, 6rem);
  font-weight: 900;
  color: var(--color-text-light);
  margin: 0.5rem 0;
  line-height: 1;
}

.name-line {
  display: block;
  background: linear-gradient(45deg, var(--color-text-light) 0%, var(--accent-mid) 100%);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
  animation: fadeInUp 0.8s ease 0.4s both;
}

.name-line.last-name {
  animation-delay: 0.6s;
  border-bottom: 3px solid var(--accent-mid);
  padding-bottom: 0.1em;
  line-height: 1.2;
}

.title-container {
  display: flex;
  align-items: center;
  gap: 0.5rem;
  margin: 1.5rem 0;
  /* Instant appearance animation */
  animation: fadeInUp 0.8s ease 0.8s both; 
}

.title {
  font-size: 1.7rem;
  color: var(--text-muted);
  margin: 0;
  font-weight: 500;
  /* Remove typing-related styles */
  overflow: visible; 
  white-space: normal; 
  width: auto; 
}

.title-cursor {
  width: 4px;
  height: 1.8rem;
  background: var(--accent-mid);
  /* Regular blink animation */
  animation: blink 0.7s step-end infinite; 
}

.description-container {
  animation: fadeInUp 0.8s ease 1s both; 
}

.description {
  font-size: 1.15rem;
  color: var(--text-soft);
  line-height: 1.8;
  margin: 1.5rem 0 2rem;
  max-width: 550px;
}

/* Restored Button Styles */
.hero-buttons {
  display: flex;
  gap: 1rem;
  flex-wrap: wrap;
  margin: 2rem 0;
  animation: fadeInUp 0.8s ease 1.2s both; 
}

.btn {
  padding: 1.1rem 2.2rem;
  border-radius: 12px;
  text-decoration: none;
  font-weight: 600;
  transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
  display: flex;
  align-items: center;
  gap: 0.75rem;
  position: relative;
  overflow: hidden;
  border: 1px solid transparent; 
}

.btn::before {
  content: '';
  position: absolute;
  top: 0;
  left: -100%;
  width: 100%;
  height: 100%;
  background: linear-gradient(90deg, transparent, rgba(255, 248, 240, 0.1), transparent);
  transition: left 0.5s ease;
}

.btn:hover::before {
  left: 100%;
}

.btn-primary {
  background: linear-gradient(135deg, var(--accent-mid) 0%, var(--accent-dark) 100%);
  color: var(--color-text-light);
  box-shadow: 0 8px 25px rgba(146, 20, 12, 0.35);
}

.btn-primary:hover {
  transform: translateY(-3px) scale(1.02);
  box-shadow: 0 12px 35px rgba(146, 20, 12, 0.5);
}

.btn-secondary {
  background: transparent;
  color: var(--accent-mid); 
  border: 1px solid var(--accent-mid); 
}

.btn-secondary:hover {
  background: rgba(146, 20, 12, 0.1);
  transform: translateY(-3px);
  box-shadow: 0 8px 25px rgba(0, 0, 0, 0.35);
}


/* Image Area - Circular Photo */
.hero-image-area {
  display: flex;
  justify-content: center;
  align-items: center;
  animation: fadeInUp 1s ease 0.4s both; 
}

.image-container {
  position: relative;
  width: 100%;
  max-width: 450px;
  padding: 20px;
  z-index: 1; 
  transition: transform 0.3s ease;
}

.image-placeholder {
  width: 100%;
  padding-top: 100%; 
  border-radius: 50%; /* CIRCLE SHAPE */
  position: relative;
  background: var(--bg-deep); 
  box-shadow: 0 15px 50px rgba(0, 0, 0, 0.6);
  overflow: hidden;
  z-index: 2;
}

.profile-image {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  object-fit: cover;
  border-radius: 50%; /* CIRCLE SHAPE */
  border: 4px solid var(--accent-mid); 
  transition: all 0.5s cubic-bezier(0.4, 0, 0.2, 1);
}

.image-glow {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  width: 100%;
  height: 100%;
  border-radius: 50%; /* CIRCLE SHAPE */
  background: radial-gradient(circle at 10% 90%, rgba(146, 20, 12, 0.5) 0%, transparent 60%);
  z-index: 1;
  animation: spotlightMove 8s ease-in-out infinite; 
}

/* Tech badges positioned relative to the image */
.tech-badge {
  position: absolute;
  background: rgba(146, 20, 12, 0.08);
  backdrop-filter: blur(10px);
  border: 1px solid rgba(146, 20, 12, 0.3);
  border-radius: 20px;
  padding: 0.5rem 1rem;
  font-size: 0.8rem;
  font-weight: 600;
  color: var(--color-text-light);
  animation: dropIn 1s ease-out infinite alternate;
  z-index: 3;
}

.badge-1 {
  top: 5%;
  left: -5%;
  animation-delay: 0s;
}

.badge-2 {
  bottom: 5%;
  left: -5%;
  animation-delay: 0.5s;
}

.badge-3 {
  top: 15%;
  right: -5%;
  animation-delay: 1s;
}

.badge-4 {
  bottom: 10%;
  right: -5%;
  animation-delay: 1.5s;
}

/* --- ANIMATIONS --- */
@keyframes slideInLeft {
  from { opacity: 0; transform: translateX(-50px); }
  to { opacity: 1; transform: translateX(0); }
}

@keyframes dropIn {
    0% { transform: translateY(-50px); opacity: 0; }
    100% { transform: translateY(0); opacity: 1; }
}

@keyframes fadeInUp {
  from { opacity: 0; transform: translateY(30px); }
  to { opacity: 1; transform: translateY(0); }
}

@keyframes blink {
  0%, 100% { opacity: 1; }
  50% { opacity: 0; }
}

@keyframes spotlightMove {
    0%, 100% {
        transform: translate(-50%, -50%) rotate(0deg) scale(1);
        opacity: 0.6;
    }
    50% {
        transform: translate(-45%, -55%) rotate(5deg) scale(1.05);
        opacity: 0.8;
    }
}


/* Responsive design */
@media (max-width: 968px) {
  .hero-content {
    grid-template-columns: 1fr;
    text-align: center;
    gap: 3rem;
  }

  .hero-text-area {
    order: 1;
    padding-right: 0;
    display: flex;
    flex-direction: column;
    align-items: center;
  }

  .description {
    max-width: 100%;
  }

  .name {
    font-size: 3.5rem;
  }
  
  .hero-image-area {
    order: 0;
  }
  
  .image-container {
      max-width: 350px;
  }

  .accent-anchor-block {
    display: none;
  }

  .tech-badge {
    position: static;
    margin: 0.5rem;
    animation: none;
  }
  
  .hero-image-area .image-container {
      display: flex;
      flex-direction: column;
      align-items: center;
      padding: 0;
  }
}

@media (max-width: 480px) {
  .name {
    font-size: 2.8rem;
  }

  .image-placeholder {
    width: 280px;
    height: 280px;
  }

  .btn {
    padding: 1rem 1.8rem;
    font-size: 0.9rem;
  }
}
</style>