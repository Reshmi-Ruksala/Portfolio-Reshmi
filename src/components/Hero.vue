<template>
  <section id="home" class="hero">
    <!-- Animated background elements -->
    <div class="hero-background">
      <div class="floating-shape shape-1"></div>
      <div class="floating-shape shape-2"></div>
      <div class="floating-shape shape-3"></div>
      <div class="floating-shape shape-4"></div>
      <div class="grid-overlay"></div>
    </div>

    <div class="hero-content">
      <div class="hero-text">
        <!-- Animated greeting -->
        <div class="greeting-container">
          <p class="greeting">Hello, I'm</p>
          <div class="greeting-underline"></div>
        </div>

        <!-- Animated name -->
        <h1 class="name">
          <span class="name-line">Reshmi</span>
          <span class="name-line last-name">Ruksala</span>
        </h1>

        <!-- Animated title with typing effect -->
        <div class="title-container">
          <p class="title">Full Stack Developer</p>
          <div class="title-cursor"></div>
        </div>

        <!-- Enhanced description -->
        <div class="description-container">
          <p class="description">
            full-stack developer with a strong focus 
          on backend engineering and building scalable, high-performance systems. 
          With experience completing 6+ full-stack projects and working with international clients, I specialize in 
          crafting modern web applications, cloud-powered solutions, and clean user experiences using modern technologies
          </p>
        </div>

        <!-- Enhanced buttons with icons -->
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

      <div class="hero-image">
        <!-- Enhanced image container with multiple animations -->
        <div class="image-container">
          <div class="image-placeholder">
            <img :src="binadaPic" alt="Binada Pasandul" class="profile-image" />
          </div>
          
          <!-- Floating tech badges -->
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
          
          <!-- Glow effect -->
          <div class="image-glow"></div>
        </div>
      </div>
    </div>

    <!-- Enhanced scroll indicator -->
    <div class="scroll-indicator" @click="handleNavClick('#about')">
      <div class="scroll-text">Scroll to explore</div>
      <div class="scroll-arrow">
        <span></span>
      </div>
    </div>
  </section>
</template>

<script setup lang="ts">
import binadaPic from '../assets/binada.jpeg'

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
.hero {
  --accent-light: #f5f5f5;
  --accent-mid: #cfcfcf;
  --accent-dark: #9a9a9a;
  --bg-deep: #050505;
  --bg-dark: #101010;
  --bg-overlay: rgba(255, 255, 255, 0.06);
  --text-muted: #bdbdbd;
  --text-soft: #dcdcdc;
  min-height: 100vh;
  display: flex;
  align-items: center;
  justify-content: center;
  padding: 120px 2rem 2rem;
  background: linear-gradient(135deg, #030303 0%, #0a0a0a 45%, #111111 100%);
  position: relative;
  overflow: hidden;
}

/* Enhanced background with animations */
.hero-background {
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  pointer-events: none;
}

.floating-shape {
  position: absolute;
  border-radius: 50%;
  background: radial-gradient(circle, rgba(255, 255, 255, 0.08) 0%, transparent 70%);
  animation: float 8s ease-in-out infinite;
}

.shape-1 {
  width: 120px;
  height: 120px;
  top: 10%;
  left: 10%;
  animation-delay: 0s;
}

.shape-2 {
  width: 80px;
  height: 80px;
  top: 60%;
  right: 15%;
  animation-delay: 2s;
}

.shape-3 {
  width: 150px;
  height: 150px;
  bottom: 10%;
  left: 20%;
  animation-delay: 4s;
}

.shape-4 {
  width: 100px;
  height: 100px;
  top: 20%;
  right: 25%;
  animation-delay: 6s;
}

.grid-overlay {
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background-image: 
    linear-gradient(rgba(255, 255, 255, 0.06) 1px, transparent 1px),
    linear-gradient(90deg, rgba(255, 255, 255, 0.06) 1px, transparent 1px);
  background-size: 50px 50px;
  animation: gridMove 20s linear infinite;
}

.hero-content {
  max-width: 1200px;
  width: 100%;
  display: grid;
  grid-template-columns: 1.2fr 1fr;
  gap: 4rem;
  align-items: center;
  z-index: 1;
  position: relative;
}

/* Enhanced text animations */
.hero-text {
  animation: slideInLeft 1s ease;
}

.greeting-container {
  position: relative;
  display: inline-block;
  margin-bottom: 0.5rem;
}

.greeting {
  font-size: 1.3rem;
  color: var(--accent-mid);
  margin-bottom: 0.5rem;
  font-weight: 500;
  animation: fadeInUp 0.8s ease 0.2s both;
}

.greeting-underline {
  position: absolute;
  bottom: -5px;
  left: 0;
  width: 0;
  height: 2px;
  background: linear-gradient(135deg, var(--accent-mid) 0%, var(--accent-dark) 100%);
  animation: expandWidth 1s ease 0.5s forwards;
}

.name {
  font-size: 4.5rem;
  font-weight: 800;
  color: #fff;
  margin: 0.5rem 0;
  line-height: 1.1;
}

.name-line {
  display: block;
  background: linear-gradient(135deg, #ffffff 0%, #dcdcdc 50%, #a0a0a0 100%);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
  animation: fadeInUp 0.8s ease 0.4s both;
}

.name-line.last-name {
  animation-delay: 0.6s;
}

.title-container {
  display: flex;
  align-items: center;
  gap: 0.5rem;
  margin: 1rem 0;
  animation: fadeInUp 0.8s ease 0.8s both;
}

.title {
  font-size: 1.6rem;
  color: var(--text-muted);
  margin: 0;
  font-weight: 500;
}

.title-cursor {
  width: 3px;
  height: 1.6rem;
  background: var(--accent-mid);
  animation: blink 1s infinite;
}

.description-container {
  animation: fadeInUp 0.8s ease 1s both;
}

.description {
  font-size: 1.15rem;
  color: var(--text-soft);
  line-height: 1.8;
  margin: 1.5rem 0 2rem;
  max-width: 500px;
}

.highlight {
  color: var(--accent-mid);
  font-weight: 600;
  position: relative;
}

.highlight::after {
  content: '';
  position: absolute;
  bottom: -2px;
  left: 0;
  width: 100%;
  height: 2px;
  background: linear-gradient(135deg, var(--accent-mid) 0%, var(--accent-dark) 100%);
  border-radius: 1px;
}

/* Enhanced buttons */
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
  border: 1px solid rgba(255, 255, 255, 0.12);
}

.btn::before {
  content: '';
  position: absolute;
  top: 0;
  left: -100%;
  width: 100%;
  height: 100%;
  background: linear-gradient(90deg, transparent, rgba(255,255,255,0.1), transparent);
  transition: left 0.5s ease;
}

.btn:hover::before {
  left: 100%;
}

.btn-primary {
  background: linear-gradient(135deg, #f2f2f2 0%, #c8c8c8 100%);
  color: #050505;
  box-shadow: 0 8px 25px rgba(0, 0, 0, 0.35);
}

.btn-primary:hover {
  transform: translateY(-3px) scale(1.02);
  box-shadow: 0 12px 35px rgba(0, 0, 0, 0.45);
}

.btn-secondary {
  background: rgba(255, 255, 255, 0.04);
  color: #f5f5f5;
  border: 1px solid rgba(255, 255, 255, 0.2);
  backdrop-filter: blur(10px);
}

.btn-secondary:hover {
  background: rgba(255, 255, 255, 0.12);
  transform: translateY(-3px);
  box-shadow: 0 8px 25px rgba(0, 0, 0, 0.35);
}

/* Enhanced image section */
.hero-image {
  display: flex;
  justify-content: center;
  align-items: center;
  animation: slideInRight 1s ease;
}

.image-container {
  position: relative;
}

.image-placeholder {
  width: 420px;
  height: 420px;
  border-radius: 50%;
  position: relative;
  background: linear-gradient(135deg, #1b1b1b 0%, #2e2e2e 100%);
  display: flex;
  align-items: center;
  justify-content: center;
  box-shadow: 0 25px 70px rgba(0, 0, 0, 0.45);
  animation: float 6s ease-in-out infinite;
  padding: 12px;
  overflow: hidden;
  z-index: 2;
}

.profile-image {
  width: 100%;
  height: 100%;
  border-radius: 50%;
  object-fit: cover;
  border: 4px solid rgba(255, 255, 255, 0.2);
  transition: all 0.3s ease;
}

.image-placeholder:hover .profile-image {
  transform: scale(1.05);
}

.image-glow {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  width: 450px;
  height: 450px;
  border-radius: 50%;
  background: radial-gradient(circle, rgba(255, 255, 255, 0.16) 0%, transparent 70%);
  animation: pulseGlow 4s ease-in-out infinite;
  z-index: 1;
}

/* Tech badges */
.tech-badge {
  position: absolute;
  background: rgba(255, 255, 255, 0.08);
  backdrop-filter: blur(10px);
  border: 1px solid rgba(255, 255, 255, 0.22);
  border-radius: 20px;
  padding: 0.5rem 1rem;
  font-size: 0.8rem;
  font-weight: 600;
  color: #f5f5f5;
  animation: float 4s ease-in-out infinite;
  z-index: 3;
}

.badge-1 {
  top: 20%;
  right: 10%;
  animation-delay: 0s;
}

.badge-2 {
  top: 60%;
  right: -10%;
  animation-delay: 1s;
}

.badge-3 {
  bottom: 20%;
  left: 10%;
  animation-delay: 2s;
}

.badge-4 {
  top: 10%;
  left: -5%;
  animation-delay: 3s;
}

/* Enhanced scroll indicator */
.scroll-indicator {
  position: absolute;
  bottom: 2rem;
  left: 50%;
  transform: translateX(-50%);
  animation: bounce 2s infinite;
  cursor: pointer;
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 0.5rem;
}

.scroll-text {
  color: var(--text-muted);
  font-size: 0.9rem;
  font-weight: 500;
  margin-bottom: 0.5rem;
}

.scroll-arrow {
  width: 30px;
  height: 50px;
  border: 2px solid var(--text-muted);
  border-radius: 25px;
  position: relative;
}

.scroll-arrow span {
  position: absolute;
  top: 10px;
  left: 50%;
  transform: translateX(-50%);
  width: 6px;
  height: 6px;
  background: var(--text-muted);
  border-radius: 50%;
  animation: scroll 2s infinite;
}

/* Animations */
@keyframes slideInLeft {
  from {
    opacity: 0;
    transform: translateX(-50px);
  }
  to {
    opacity: 1;
    transform: translateX(0);
  }
}

@keyframes slideInRight {
  from {
    opacity: 0;
    transform: translateX(50px);
  }
  to {
    opacity: 1;
    transform: translateX(0);
  }
}

@keyframes fadeInUp {
  from {
    opacity: 0;
    transform: translateY(30px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

@keyframes expandWidth {
  to {
    width: 100%;
  }
}

@keyframes blink {
  0%, 100% { opacity: 1; }
  50% { opacity: 0; }
}

@keyframes float {
  0%, 100% {
    transform: translateY(0) rotate(0deg);
  }
  50% {
    transform: translateY(-20px) rotate(5deg);
  }
}

@keyframes gridMove {
  0% {
    transform: translate(0, 0);
  }
  100% {
    transform: translate(50px, 50px);
  }
}

@keyframes pulseGlow {
  0%, 100% {
    opacity: 0.5;
    transform: translate(-50%, -50%) scale(1);
  }
  50% {
    opacity: 0.8;
    transform: translate(-50%, -50%) scale(1.1);
  }
}

@keyframes bounce {
  0%, 100% {
    transform: translateX(-50%) translateY(0);
  }
  50% {
    transform: translateX(-50%) translateY(-10px);
  }
}

@keyframes scroll {
  0% {
    opacity: 1;
    top: 10px;
  }
  100% {
    opacity: 0;
    top: 30px;
  }
}

/* Responsive design */
@media (max-width: 968px) {
  .hero-content {
    grid-template-columns: 1fr;
    text-align: center;
    gap: 3rem;
  }

  .hero-text {
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

  .image-placeholder {
    width: 320px;
    height: 320px;
  }

  .tech-badge {
    display: none;
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