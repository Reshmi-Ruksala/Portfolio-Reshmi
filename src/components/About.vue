<template>
  <section id="about" class="about">
    <div class="container">
      <div class="section-header">
        <span class="section-label">About Me</span>
        <h2 class="section-title">
          A Little <span class="title-accent">About</span> Myself
        </h2>
        <p class="section-subtitle">
          Passionate developer crafting digital solutions with precision and creativity
        </p>
      </div>

      <div class="about-content">
        <div class="about-text">
          <p>
            I'm Reshmi Ruksala, an IT undergraduate at SLIIT and a dedicated full-stack developer with strong expertise in backend development, cloud computing, and scalable 
            system architecture. Over the past few years, I've completed 6+ full-stack projects across MERN, Java JSP/Servlet, PHP-MySQL, and Android, gaining hands-on experience building secure APIs, 
            real-time applications, and production-ready platforms. 
            I've worked with international clients, including delivering a real-time trading project integrating React, C#, SignalR, and WebSockets using Agile and Jira.
          </p>
          <p>
            I'm skilled in technologies such as Java, JavaScript, Python, C#, React.js, Node.js, SQL, MongoDB, AWS, Azure, and 
            .NET — and I enjoy turning complex requirements into clean, efficient, and well-designed systems. Beyond development, I value continuous
             learning, problem-solving, and writing maintainable code that scales. My goal is to grow as a backend and cloud engineer while creating high-quality digital solutions
             that make a real impact.
          </p>
        </div>

        <div class="about-image">
          <div class="image-wrapper">
            <img :src="binadaPic" alt="Reshmi Ruksala" class="about-profile-image" />
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup lang="ts">
import binadaPic from '../assets/binada.png'
</script>

<style scoped>
.about {
  /* Color Variables */
  --color-primary: #92140C; /* Deep Crimson Accent */
  --color-text-light: #FFF8F0; /* Off-White/Cream Text */
  --color-bg-deep: #1E1E24; /* Deep Charcoal Background */
  --color-bg-dark: #2A2A35; /* Slightly lighter charcoal */
  --accent-mid: var(--color-primary);
  --text-muted: #b3a093; /* Muted brown-gray */

  padding: 120px 2rem;
  background: var(--color-bg-deep);
  min-height: 100vh;
  width: 100%;
  box-sizing: border-box;
  overflow-x: hidden;
  position: relative;
}

.about::before {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  height: 1px;
  background: linear-gradient(90deg, transparent, rgba(146, 20, 12, 0.5), transparent);
}

.container {
  max-width: 1400px;
  margin: 0 auto;
}

/* Section Header */
.section-header {
  text-align: center;
  margin-bottom: 4rem;
  animation: fadeInUp 0.8s ease;
}

.section-label {
  display: inline-block;
  font-size: 0.9rem;
  color: var(--accent-mid);
  text-transform: uppercase;
  letter-spacing: 3px;
  font-weight: 600;
  margin-bottom: 1rem;
  position: relative;
  padding-left: 2rem;
}

.section-label::before {
  content: '';
  position: absolute;
  left: 0;
  top: 50%;
  transform: translateY(-50%);
  width: 1.5rem;
  height: 2px;
  background: var(--accent-mid);
}

.section-title {
  font-size: clamp(2.5rem, 5vw, 4rem);
  color: var(--color-text-light);
  margin: 0.5rem 0 1rem;
  font-weight: 800;
  line-height: 1.2;
}

.title-accent {
  color: var(--accent-mid);
}

.section-subtitle {
  font-size: 1.1rem;
  color: var(--text-muted);
  max-width: 600px;
  margin: 0 auto;
  line-height: 1.6;
}

/* About Content */
.about-content {
  display: grid;
  grid-template-columns: 1.2fr 1fr;
  gap: 4rem;
  align-items: center;
}

.about-text {
  color: var(--text-muted);
  line-height: 1.8;
  font-size: 1.05rem;
  animation: fadeInLeft 0.8s ease;
}

.about-text p {
  margin-bottom: 1.5rem;
}

.about-text p:last-child {
  margin-bottom: 0;
}

/* Image Section */
.about-image {
  display: flex;
  justify-content: center;
  align-items: center;
  animation: fadeInRight 0.8s ease;
}

.image-wrapper {
  position: relative;
  width: 100%;
  max-width: 400px;
  border-radius: 20px;
  overflow: hidden;
  border: 2px solid rgba(146, 20, 12, 0.2);
  transition: all 0.4s ease;
}

.image-wrapper:hover {
  border-color: rgba(146, 20, 12, 0.4);
  transform: translateY(-5px);
  box-shadow: 0 15px 40px rgba(146, 20, 12, 0.2);
}

.about-profile-image {
  width: 100%;
  height: auto;
  display: block;
  object-fit: cover;
}

/* Animations */
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

@keyframes fadeInLeft {
  from {
    opacity: 0;
    transform: translateX(-30px);
  }
  to {
    opacity: 1;
    transform: translateX(0);
  }
}

@keyframes fadeInRight {
  from {
    opacity: 0;
    transform: translateX(30px);
  }
  to {
    opacity: 1;
    transform: translateX(0);
  }
}


/* Responsive */
@media (max-width: 968px) {
  .about-content {
    grid-template-columns: 1fr;
    gap: 3rem;
  }

  .about-image {
    order: -1;
  }
}

@media (max-width: 768px) {
  .about {
    padding: 80px 1.5rem;
  }

  .section-header {
    margin-bottom: 3rem;
  }
}
</style>

