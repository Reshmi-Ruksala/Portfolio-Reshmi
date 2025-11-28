<template>
  <nav class="navbar" :class="{ scrolled: isScrolled, 'menu-open': isMenuOpen }">
    <div class="nav-container">
      <div class="logo">
        <a href="#home" @click.prevent="handleNavClick('#home')">
          <div class="logo-icon">
            <div class="logo-dot"></div>
            <div class="logo-line"></div>
          </div>
          <span>Binada Pasandul</span>
        </a>
      </div>
      <ul class="nav-menu" :class="{ active: isMenuOpen }">
        <li><a href="#home" @click.prevent="handleNavClick('#home')" :class="{ active: activeSection === 'home' }">
          <span class="nav-text">Home</span>
          <div class="nav-highlight"></div>
        </a></li>
        <li><a href="#about" @click.prevent="handleNavClick('#about')" :class="{ active: activeSection === 'about' }">
          <span class="nav-text">About</span>
          <div class="nav-highlight"></div>
        </a></li>
        <li><a href="#skills" @click.prevent="handleNavClick('#skills')" :class="{ active: activeSection === 'skills' }">
          <span class="nav-text">Skills</span>
          <div class="nav-highlight"></div>
        </a></li>
        <li><a href="#projects" @click.prevent="handleNavClick('#projects')" :class="{ active: activeSection === 'projects' }">
          <span class="nav-text">Projects</span>
          <div class="nav-highlight"></div>
        </a></li>
        <li><a href="#contact" @click.prevent="handleNavClick('#contact')" :class="{ active: activeSection === 'contact' }">
          <span class="nav-text">Contact</span>
          <div class="nav-highlight"></div>
        </a></li>
      </ul>
      <div class="nav-actions">
        <!-- Updated Resume Button -->
        <button class="resume-btn" @click="downloadResume">
          <span>Resume</span>
          <svg width="16" height="16" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
            <path d="M14 2H6C5.46957 2 4.96086 2.21071 4.58579 2.58579C4.21071 2.96086 4 3.46957 4 4V20C4 20.5304 4.21071 21.0391 4.58579 21.4142C4.96086 21.7893 5.46957 22 6 22H18C18.5304 22 19.0391 21.7893 19.4142 21.4142C19.7893 21.0391 20 20.5304 20 20V8M14 2L20 8M14 2V8H20" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
          </svg>
        </button>
      </div>
      <div class="hamburger" @click="toggleMenu" :class="{ active: isMenuOpen }">
        <span></span>
        <span></span>
        <span></span>
      </div>
    </div>
    
    <!-- Animated background elements -->
    <div class="nav-background">
      <div class="bg-shape shape-1"></div>
      <div class="bg-shape shape-2"></div>
      <div class="bg-shape shape-3"></div>
    </div>
  </nav>
</template>

<script setup lang="ts">
import { ref, onMounted, onUnmounted } from 'vue'

const isScrolled = ref(false)
const isMenuOpen = ref(false)
const activeSection = ref('home')

const handleScroll = () => {
  isScrolled.value = window.scrollY > 50
  
  // Update active section based on scroll position
  const sections = ['home', 'about', 'skills', 'projects', 'contact']

  
  for (const section of sections) {
    const element = document.getElementById(section)
    if (element) {
      const rect = element.getBoundingClientRect()
      if (rect.top <= 100 && rect.bottom >= 100) {
        activeSection.value = section
        break
      }
    }
  }
}

const toggleMenu = () => {
  isMenuOpen.value = !isMenuOpen.value
}

// Fixed navigation function
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
    
    // Update active section immediately
    activeSection.value = sectionId.substring(1)
  }
  closeMenu()
}

// Resume download function
const downloadResume = () => {
  // Create a temporary anchor element
  const link = document.createElement('a')
  link.href = '/resume.pdf'
  link.download = 'Binada_Pasandul_Resume.pdf' // This will be the downloaded file name
  document.body.appendChild(link)
  link.click()
  document.body.removeChild(link)
  closeMenu()
}

const closeMenu = () => {
  isMenuOpen.value = false
}

onMounted(() => {
  window.addEventListener('scroll', handleScroll)
  // Set initial active section
  handleScroll()
})

onUnmounted(() => {
  window.removeEventListener('scroll', handleScroll)
})
</script>

<style scoped>
/* Updated colors for black hero section */
.navbar {
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  background: rgba(0, 0, 0, 0.9);
  backdrop-filter: blur(15px);
  -webkit-backdrop-filter: blur(15px);
  border-bottom: 1px solid rgba(255, 255, 255, 0.1);
  z-index: 1000;
  transition: all 0.4s cubic-bezier(0.25, 0.46, 0.45, 0.94);
  padding: 1.2rem 0;
  overflow: hidden;
}

.navbar.scrolled {
  background: rgba(0, 0, 0, 0.95);
  box-shadow: 0 4px 30px rgba(0, 0, 0, 0.5);
  padding: 0.8rem 0;
  border-bottom: 1px solid rgba(255, 255, 255, 0.15);
}

.nav-container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 2rem;
  display: flex;
  justify-content: space-between;
  align-items: center;
  position: relative;
  z-index: 2;
}

.logo a {
  display: flex;
  align-items: center;
  gap: 0.75rem;
  font-size: 1.5rem;
  font-weight: 700;
  background: linear-gradient(135deg, #fff 0%, #667eea 100%);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
  text-decoration: none;
  transition: all 0.3s ease;
  position: relative;
  overflow: hidden;
  cursor: pointer;
}

.logo a::before {
  content: '';
  position: absolute;
  bottom: -2px;
  left: 0;
  width: 0;
  height: 2px;
  background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
  transition: width 0.3s ease;
  border-radius: 2px;
}

.logo a:hover::before {
  width: 100%;
}

.logo-icon {
  position: relative;
  width: 32px;
  height: 32px;
  display: flex;
  align-items: center;
  justify-content: center;
}

.logo-dot {
  width: 8px;
  height: 8px;
  background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
  border-radius: 50%;
  position: absolute;
  animation: pulse 2s infinite;
}

.logo-line {
  width: 20px;
  height: 2px;
  background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
  border-radius: 1px;
  transform: rotate(45deg);
  animation: rotate 8s linear infinite;
}

.nav-menu {
  display: flex;
  list-style: none;
  gap: 2.5rem;
  margin: 0;
  padding: 0;
}

.nav-menu li {
  position: relative;
}

.nav-menu li a {
  color: rgba(255, 255, 255, 0.8);
  text-decoration: none;
  font-weight: 500;
  font-size: 0.95rem;
  transition: all 0.3s ease;
  position: relative;
  padding: 0.5rem 0;
  display: flex;
  flex-direction: column;
  align-items: center;
  overflow: hidden;
  cursor: pointer;
}

.nav-text {
  position: relative;
  z-index: 1;
  transition: all 0.3s ease;
}

.nav-highlight {
  position: absolute;
  bottom: 0;
  left: 0;
  width: 0;
  height: 2px;
  background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
  transition: width 0.3s ease;
  border-radius: 2px;
}

.nav-menu li a:hover .nav-text,
.nav-menu li a.active .nav-text {
  color: #fff;
  transform: translateY(-2px);
}

.nav-menu li a:hover .nav-highlight,
.nav-menu li a.active .nav-highlight {
  width: 100%;
}

.nav-actions {
  display: flex;
  align-items: center;
}

.resume-btn {
  display: flex;
  align-items: center;
  gap: 0.5rem;
  background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
  color: white;
  text-decoration: none;
  padding: 0.7rem 1.5rem;
  border-radius: 8px;
  font-weight: 500;
  font-size: 0.9rem;
  transition: all 0.3s ease;
  box-shadow: 0 4px 15px rgba(102, 126, 234, 0.3);
  position: relative;
  overflow: hidden;
  border: none;
  cursor: pointer;
  font-family: inherit;
}

.resume-btn::before {
  content: '';
  position: absolute;
  top: 0;
  left: -100%;
  width: 100%;
  height: 100%;
  background: linear-gradient(90deg, transparent, rgba(255,255,255,0.2), transparent);
  transition: left 0.5s ease;
}

.resume-btn:hover::before {
  left: 100%;
}

.resume-btn:hover {
  transform: translateY(-2px);
  box-shadow: 0 6px 20px rgba(102, 126, 234, 0.5);
}

.hamburger {
  display: none;
  flex-direction: column;
  cursor: pointer;
  gap: 4px;
  padding: 0.5rem;
  border-radius: 6px;
  transition: all 0.3s ease;
  position: relative;
  z-index: 10;
}

.hamburger:hover {
  background: rgba(102, 126, 234, 0.1);
}

.hamburger span {
  width: 22px;
  height: 2px;
  background: rgba(255, 255, 255, 0.8);
  transition: all 0.3s ease;
  border-radius: 2px;
}

.hamburger.active span:nth-child(1) {
  transform: rotate(45deg) translate(6px, 6px);
  background: #667eea;
}

.hamburger.active span:nth-child(2) {
  opacity: 0;
}

.hamburger.active span:nth-child(3) {
  transform: rotate(-45deg) translate(6px, -6px);
  background: #667eea;
}

/* Animated background elements */
.nav-background {
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  pointer-events: none;
  z-index: 1;
  overflow: hidden;
}

.bg-shape {
  position: absolute;
  border-radius: 50%;
  background: radial-gradient(circle, rgba(102, 126, 234, 0.1) 0%, transparent 70%);
  animation: float 6s ease-in-out infinite;
}

.shape-1 {
  width: 100px;
  height: 100px;
  top: -50px;
  left: 10%;
  animation-delay: 0s;
}

.shape-2 {
  width: 150px;
  height: 150px;
  top: -75px;
  right: 15%;
  animation-delay: 2s;
}

.shape-3 {
  width: 80px;
  height: 80px;
  bottom: -40px;
  left: 20%;
  animation-delay: 4s;
}

/* Animations - All kept the same */
@keyframes pulse {
  0%, 100% {
    transform: scale(1);
    opacity: 1;
  }
  50% {
    transform: scale(1.2);
    opacity: 0.8;
  }
}

@keyframes rotate {
  from {
    transform: rotate(0deg);
  }
  to {
    transform: rotate(360deg);
  }
}

@keyframes float {
  0%, 100% {
    transform: translateY(0) rotate(0deg);
  }
  33% {
    transform: translateY(-10px) rotate(120deg);
  }
  66% {
    transform: translateY(5px) rotate(240deg);
  }
}

@keyframes slideIn {
  from {
    opacity: 0;
    transform: translateY(-10px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

/* Mobile styles */
@media (max-width: 768px) {
  .nav-actions {
    display: none;
  }
  
  .hamburger {
    display: flex;
  }

  .nav-menu {
    position: fixed;
    left: -100%;
    top: 100%;
    flex-direction: column;
    background: rgba(0, 0, 0, 0.98);
    backdrop-filter: blur(20px);
    -webkit-backdrop-filter: blur(20px);
    width: 100%;
    text-align: center;
    transition: all 0.4s cubic-bezier(0.25, 0.46, 0.45, 0.94);
    padding: 2rem 0;
    gap: 0;
    border-top: 1px solid rgba(255, 255, 255, 0.1);
    box-shadow: 0 10px 30px rgba(0, 0, 0, 0.5);
  }

  .nav-menu.active {
    left: 0;
  }

  .nav-menu li {
    width: 100%;
    animation: slideIn 0.3s ease forwards;
    opacity: 0;
  }

  .nav-menu.active li:nth-child(1) { animation-delay: 0.1s; }
  .nav-menu.active li:nth-child(2) { animation-delay: 0.2s; }
  .nav-menu.active li:nth-child(3) { animation-delay: 0.3s; }
  .nav-menu.active li:nth-child(4) { animation-delay: 0.4s; }
  .nav-menu.active li:nth-child(5) { animation-delay: 0.5s; }

  .nav-menu li a {
    display: block;
    padding: 1.2rem 2rem;
    border-bottom: 1px solid rgba(255, 255, 255, 0.1);
    flex-direction: row;
    justify-content: center;
  }

  .nav-menu li:last-child a {
    border-bottom: none;
  }

  .nav-highlight {
    display: none;
  }

  .navbar.menu-open {
    background: rgba(0, 0, 0, 0.98);
    backdrop-filter: blur(20px);
  }
}

@media (max-width: 480px) {
  .nav-container {
    padding: 0 1rem;
  }
  
  .logo a span {
    font-size: 1.25rem;
  }
  
  .logo-icon {
    width: 28px;
    height: 28px;
  }
}
</style>