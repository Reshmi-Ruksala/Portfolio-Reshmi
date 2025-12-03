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
            I'm <strong>Reshmi Ruksala</strong>, an IT undergraduate at <strong>SLIIT</strong> and a dedicated <strong>full-stack developer</strong> with strong expertise in backend development, cloud computing, and scalable 
            system architecture. Over the past few years, I've completed <strong>6+ full-stack projects</strong> across MERN, Java JSP/Servlet, PHP-MySQL, and Android, gaining hands-on experience building secure APIs, 
            real-time applications, and production-ready platforms. 
            I've worked with international clients, including delivering a real-time trading project integrating React, C#, SignalR, and WebSockets using <strong>Agile and Jira</strong>.
          </p>
          <p>
            I'm skilled in technologies such as <strong>Java</strong>, <strong>JavaScript</strong>, <strong>Python</strong>, <strong>C#</strong>, <strong>React.js</strong>, <strong>Node.js</strong>, <strong>SQL</strong>, <strong>MongoDB</strong>, <strong>AWS</strong>, <strong>Azure</strong>, and 
            <strong>.NET</strong> — and I enjoy turning complex requirements into clean, efficient, and well-designed systems. Beyond development, I value continuous
            learning, problem-solving, and writing maintainable code that scales. My goal is to grow as a <strong>backend and cloud engineer</strong> while creating high-quality digital solutions
            that make a real impact.
          </p>
        </div>

        <div class="about-image">
          <div class="image-wrapper">
            <img :src="binadaPic" alt="Reshmi Ruksala" class="about-profile-image" />
          </div>
        </div>
      </div>
      
      <div class="education-section">
          <h3 class="education-main-title">
              <span class="title-icon">🎯</span> 
              Academic Profile & <span class="title-accent">Core Focus</span>
          </h3>
          
          <div class="timeline-container">
              
              <div class="timeline-block block-degree">
                  <div class="timeline-icon">🎓</div>
                  <div class="timeline-content">
                      <p class="timeline-date">Current Undergraduate Program</p>
                      <h4 class="timeline-title">BSc (Hons) Information Technology</h4>
                      <p class="timeline-institution">Sri Lanka Institute of Information Technology (SLIIT)</p>
                      <p class="timeline-detail">Specializing in: <strong>Data Science</strong></p>
                  </div>
              </div>

              <div class="timeline-block block-focus">
                  <div class="timeline-icon">💡</div>
                  <div class="timeline-content">
                      <p class="timeline-date">Core Technical Path</p>
                      <h4 class="timeline-title">Full-Stack Development</h4>
                      <ul class="focus-list">
                          <li><span class="list-marker">→</span> Web Systems (React, Node.js, Express)</li>
                          <li><span class="list-marker">→</span> Mobile Development (Android Studio, Kotlin/Java)</li>
                          <li><span class="list-marker">→</span> Backend & Cloud Architecture (AWS, Azure, .NET)</li>
                      </ul>
                  </div>
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
  --card-glow: rgba(146, 20, 12, 0.4); /* Glow effect color */

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
  margin-bottom: 6rem;
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

/* --- NEW: Redesigned Education Section Styles (Timeline/Block Style) --- */
.education-section {
    animation: fadeInUp 0.8s ease 0.2s both; 
    padding-top: 2rem;
    max-width: 900px;
    margin: 0 auto;
}

.education-main-title {
    font-size: 2.5rem;
    color: var(--color-text-light);
    border-bottom: 3px solid var(--accent-mid);
    padding-bottom: 0.5rem;
    margin-bottom: 3rem;
    display: flex;
    align-items: center;
    gap: 0.75rem;
    font-weight: 700;
    justify-content: center;
}

.timeline-container {
    position: relative;
    padding: 0 1rem;
}

/* Vertical Line for the Timeline Effect */
.timeline-container::after {
    content: '';
    position: absolute;
    width: 3px;
    background-color: var(--accent-mid);
    top: 0;
    bottom: 0;
    left: 50%;
    margin-left: -1.5px;
    opacity: 0.2;
}

.timeline-block {
    padding: 10px 40px;
    position: relative;
    background-color: inherit;
    width: 45%;
    margin-bottom: 2rem;
    transition: transform 0.3s ease, box-shadow 0.3s ease;
}

.timeline-block:hover {
    transform: translateY(-5px);
}

.timeline-block:nth-child(even) {
    left: 50%;
}

/* Timeline Icon/Dot */
.timeline-icon {
    width: 50px;
    height: 50px;
    background-color: var(--accent-mid);
    border: 3px solid var(--color-bg-deep); /* Border to stand out on the line */
    border-radius: 50%;
    position: absolute;
    top: 15px;
    z-index: 1;
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 1.5rem;
    color: var(--color-text-light);
    box-shadow: 0 0 15px rgba(146, 20, 12, 0.6);
}

.timeline-block:nth-child(odd) .timeline-icon {
    right: -25px;
}

.timeline-block:nth-child(even) .timeline-icon {
    left: -25px;
}

/* Card Content */
.timeline-content {
    padding: 1.5rem;
    background: var(--color-bg-dark); 
    position: relative;
    border-radius: 8px;
    border: 1px solid rgba(146, 20, 12, 0.4);
    box-shadow: 0 5px 20px rgba(0, 0, 0, 0.4);
}

.timeline-content::after {
    content: " ";
    height: 0;
    position: absolute;
    top: 22px;
    width: 0;
    z-index: 1;
    border: medium solid var(--color-bg-dark);
}

.timeline-block:nth-child(odd) .timeline-content::after {
    border-width: 10px 0 10px 10px;
    border-color: transparent transparent transparent var(--color-bg-dark);
    right: -10px;
}

.timeline-block:nth-child(even) .timeline-content::after {
    border-width: 10px 10px 10px 0;
    border-color: transparent var(--color-bg-dark) transparent transparent;
    left: -10px;
}

.timeline-date {
    font-size: 0.9rem;
    color: var(--accent-mid);
    text-transform: uppercase;
    letter-spacing: 1px;
    margin-bottom: 0.5rem;
}

.timeline-title {
    font-size: 1.5rem;
    color: var(--color-text-light);
    font-weight: 700;
    margin-top: 0;
    margin-bottom: 0.5rem;
}

.timeline-institution {
    font-size: 1rem;
    color: var(--text-muted);
    font-style: italic;
    margin-bottom: 1rem;
}

.timeline-detail {
    font-size: 1rem;
    color: var(--text-muted);
}
/* Focus List Specifics */
.focus-list {
    list-style: none;
    padding: 0;
    margin: 0;
    color: var(--text-muted);
}

.focus-list li {
    padding-left: 0;
    margin-bottom: 0.4rem;
    font-size: 1rem;
}

.list-marker {
    color: var(--accent-mid);
    margin-right: 0.5rem;
    font-weight: bold;
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
    margin-bottom: 4rem; 
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

  /* Timeline Responsive Adjustments */
    .education-main-title {
        font-size: 1.8rem;
    }
    
    .timeline-container::after {
        left: 30px; /* Move vertical line to the left */
    }

    .timeline-block {
        width: 100%;
        padding-left: 70px; /* Make space for the icon on the left */
        padding-right: 15px;
        left: 0 !important; /* All blocks align left */
    }
    
    .timeline-block:nth-child(odd) .timeline-icon,
    .timeline-block:nth-child(even) .timeline-icon {
        left: 5px; /* Icon aligns with the new line position */
        right: auto;
    }

    .timeline-block:nth-child(odd) .timeline-content::after {
        border-color: transparent transparent transparent var(--color-bg-dark);
        left: 60px; /* Move arrow to the left side of the card */
        right: auto;
    }

    .timeline-block:nth-child(even) .timeline-content::after {
        border-color: transparent var(--color-bg-dark) transparent transparent;
        left: 60px; /* Move arrow to the left side of the card */
    }
}
</style>