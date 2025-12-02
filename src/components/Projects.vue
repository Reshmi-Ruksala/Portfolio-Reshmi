<template>
  <section id="projects" class="projects">
    <div class="container">
      <div class="section-header">
        <span class="section-label">My Work</span>
        <h2 class="section-title">
          Featured <span class="title-accent">Projects</span>
        </h2>
        <p class="section-subtitle">
          A collection of projects showcasing my skills and experience in full-stack development
        </p>
      </div>

      <div class="projects-grid">
        <div
          v-for="(project, index) in projects"
          :key="project.id"
          class="project-card"
          :style="{ animationDelay: `${index * 0.1}s` }"
        >
          <div class="project-image-wrapper">
            <div class="project-image">
              <img
                v-if="project.image"
                :src="project.image"
                :alt="project.title"
                class="img-fill"
              />
              <div v-else class="image-placeholder">
                <svg viewBox="0 0 24 24" fill="none" stroke="currentColor">
                  <rect x="3" y="3" width="18" height="18" rx="2" stroke-width="2"/>
                  <path d="M3 9h18M9 3v18" stroke-width="2"/>
                </svg>
              </div>
              <div class="project-overlay">
                <div class="overlay-content">
                  <a
                    :href="project.github"
                    target="_blank"
                    class="project-link"
                    title="View on GitHub"
                  >
                    <svg viewBox="0 0 24 24" fill="currentColor">
                      <path d="M12 0c-6.626 0-12 5.373-12 12 0 5.302 3.438 9.8 8.207 11.387.599.111.793-.261.793-.577v-2.234c-3.338.726-4.033-1.416-4.033-1.416-.546-1.387-1.333-1.756-1.333-1.756-1.089-.745.083-.729.083-.729 1.205.084 1.839 1.237 1.839 1.237 1.07 1.834 2.807 1.304 3.492.997.107-.775.418-1.305.762-1.604-2.665-.305-5.467-1.334-5.467-5.931 0-1.311.469-2.381 1.236-3.221-.124-.303-.535-1.524.117-3.176 0 0 1.008-.322 3.301 1.23.957-.266 1.983-.399 3.003-.404 1.02.005 2.047.138 3.006.404 2.291-1.552 3.297-1.23 3.297-1.23.653 1.653.242 2.874.118 3.176.77.84 1.235 1.911 1.235 3.221 0 4.609-2.807 5.624-5.479 5.921.43.372.823 1.102.823 2.222v3.293c0 .319.192.694.801.576 4.765-1.589 8.199-6.086 8.199-11.386 0-6.627-5.373-12-12-12z"/>
                    </svg>
                    <span>Code</span>
                  </a>
                  <a
                    v-if="project.live"
                    :href="project.live"
                    target="_blank"
                    class="project-link"
                    title="View Live"
                  >
                    <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                      <path d="M18 13v6a2 2 0 0 1-2 2H5a2 2 0 0 1-2-2V8a2 2 0 0 1 2-2h6M15 3h6v6M10 14L21 3"/>
                    </svg>
                    <span>Live</span>
                  </a>
                </div>
              </div>
            </div>
            <div class="project-number">{{ String(index + 1).padStart(2, '0') }}</div>
          </div>

          <div class="project-content">
            <div class="project-header">
              <h3 class="project-title">{{ project.title }}</h3>
              <div class="project-line"></div>
            </div>
            <p class="project-description">{{ project.description }}</p>
            <div class="project-footer">
              <div class="project-tech">
                <span
                  v-for="tech in project.technologies"
                  :key="tech"
                  class="tech-tag"
                >
                  {{ tech }}
                </span>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup lang="ts">
interface Project {
  id: number
  title: string
  description: string
  technologies: string[]
  github: string
  live?: string
  image?: string
}

const projects: Project[] = [
  {
    id: 1,
    title: 'Snazzy-The Smart Shoe Store',
    description: 'A full-stack e-commerce application with user authentication, Live chat system, stripe payment integration and admin dashboards.MERN stack',
    technologies: ['React.js', 'Node.js', 'MongoDB', 'Express'],
    github: 'https://github.com/BinadaPasandul/snazzy/tree/new',
    image: '/images/snazzy2.jpeg'
  },
  {
    id: 2,
    title: 'Bidify-Online Biding system',
    description: 'A full-stack auction system where sellers can set bids for their items and buyers can buy them and can be delivered.',
    technologies: ['Java', 'JSP/Servlet', 'SQL', 'tomcat'],
    github: 'https://github.com/BinadaPasandul/Bidify',
    image: '/images/bidify.jpeg'
  },
  {
    id: 3,
    title: 'BeWell+',
    description: 'A A wellness tracking app with daily habit tracking, water intake monitoring, and mood logging. Built using Kotlin with SharedPreferences for smooth and persistent user data storage.',
    technologies: ['Kotlin', 'Shared preferences','Figma'],
    github: 'https://github.com/Reshmi-Ruksala/BeWell-',
    image: '/images/pulse1.jpeg'
  },
  {
    id: 4,
    title: 'HomeFix',
    description: 'A Mobile App Developer Developed a mobile app for browsing, booking, and managing home services with an intuitive UI and smooth user experience. ',
    technologies: ['Kotlin','Share preferences', 'Figma'],
    github: 'https://github.com/Reshmi-Ruksala/HomeFix-MAD',
    image: '/images/travella1.jpeg'
  },
  {
    id: 5,
    title: 'Wed.In',
    description: 'A hotel reservation system for weddings using, Implemented user booking, hotel listing and admin management features',
    technologies: ['html', 'css', 'js', 'php'],
    github: 'https://github.com',
    image: '/images/wedin.jpeg'
  },
  {
    id: 6,
    title: 'Portfolio Website',
    description: 'A modern, responsive portfolio website showcasing projects, skills, and contact information with smooth animations.',
    technologies: ['Vue.js', 'TypeScript', 'Vite', 'CSS3'],
    github: 'https://github.com/Reshmi-Ruksala/Portfolio-Reshmi',
    image: '/images/portfolio1.jpeg'
  }
]
</script>

<style scoped>
.projects {
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

.projects::before {
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
  position: relative;
}

.section-subtitle {
  font-size: 1.1rem;
  color: var(--text-muted);
  max-width: 600px;
  margin: 0 auto;
  line-height: 1.6;
}

/* Projects Grid */
.projects-grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(380px, 1fr));
  gap: 2.5rem;
}

.project-card {
  background: rgba(42, 42, 53, 0.4);
  border-radius: 20px;
  overflow: hidden;
  transition: all 0.4s cubic-bezier(0.4, 0, 0.2, 1);
  border: 1px solid rgba(146, 20, 12, 0.1);
  backdrop-filter: blur(10px);
  animation: fadeInUp 0.8s ease both;
  position: relative;
}

.project-card::before {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background: linear-gradient(135deg, rgba(146, 20, 12, 0.05) 0%, transparent 50%);
  opacity: 0;
  transition: opacity 0.4s ease;
  pointer-events: none;
}

.project-card:hover {
  transform: translateY(-8px);
  box-shadow: 0 25px 50px rgba(146, 20, 12, 0.25);
  border-color: rgba(146, 20, 12, 0.3);
}

.project-card:hover::before {
  opacity: 1;
}

/* Image Wrapper */
.project-image-wrapper {
  position: relative;
  width: 100%;
  height: 280px;
  overflow: hidden;
  background: linear-gradient(135deg, rgba(146, 20, 12, 0.1) 0%, rgba(30, 30, 36, 0.5) 100%);
}

.project-image {
  position: relative;
  width: 100%;
  height: 100%;
  overflow: hidden;
}

.img-fill {
  width: 100%;
  height: 100%;
  object-fit: cover;
  transition: transform 0.6s cubic-bezier(0.4, 0, 0.2, 1);
  display: block;
}

.project-card:hover .img-fill {
  transform: scale(1.1);
}

.image-placeholder {
  width: 100%;
  height: 100%;
  display: flex;
  align-items: center;
  justify-content: center;
  color: rgba(255, 248, 240, 0.3);
  background: rgba(0, 0, 0, 0.2);
}

.image-placeholder svg {
  width: 60px;
  height: 60px;
}

.project-number {
  position: absolute;
  top: 1.5rem;
  right: 1.5rem;
  font-size: 4rem;
  font-weight: 800;
  color: rgba(146, 20, 12, 0.15);
  font-family: 'Courier New', monospace;
  line-height: 1;
  z-index: 1;
}

/* Overlay */
.project-overlay {
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background: linear-gradient(135deg, rgba(146, 20, 12, 0.95) 0%, rgba(110, 16, 10, 0.95) 100%);
  display: flex;
  align-items: center;
  justify-content: center;
  opacity: 0;
  transition: opacity 0.4s ease;
  z-index: 2;
}

.project-card:hover .project-overlay {
  opacity: 1;
}

.overlay-content {
  display: flex;
  gap: 1.5rem;
  align-items: center;
}

.project-link {
  display: flex;
  align-items: center;
  gap: 0.5rem;
  padding: 0.8rem 1.5rem;
  background: rgba(255, 248, 240, 0.1);
  border: 1px solid rgba(255, 248, 240, 0.2);
  border-radius: 12px;
  color: var(--color-text-light);
  text-decoration: none;
  font-weight: 600;
  font-size: 0.9rem;
  transition: all 0.3s ease;
  backdrop-filter: blur(10px);
}

.project-link:hover {
  background: var(--color-text-light);
  color: var(--accent-mid);
  transform: translateY(-2px);
  box-shadow: 0 8px 20px rgba(0, 0, 0, 0.3);
}

.project-link svg {
  width: 20px;
  height: 20px;
}

/* Project Content */
.project-content {
  padding: 2rem;
}

.project-header {
  display: flex;
  align-items: center;
  justify-content: space-between;
  margin-bottom: 1rem;
  gap: 1rem;
}

.project-title {
  font-size: 1.6rem;
  color: var(--color-text-light);
  margin: 0;
  font-weight: 700;
  line-height: 1.3;
  flex: 1;
}

.project-line {
  width: 60px;
  height: 3px;
  background: linear-gradient(90deg, var(--accent-mid) 0%, transparent 100%);
  border-radius: 2px;
  flex-shrink: 0;
}

.project-description {
  color: var(--text-muted);
  line-height: 1.7;
  margin-bottom: 1.5rem;
  font-size: 0.95rem;
}

.project-footer {
  display: flex;
  align-items: center;
  justify-content: space-between;
  flex-wrap: wrap;
  gap: 1rem;
}

.project-tech {
  display: flex;
  flex-wrap: wrap;
  gap: 0.6rem;
}

.tech-tag {
  padding: 0.4rem 1rem;
  background: rgba(146, 20, 12, 0.15);
  color: var(--accent-mid);
  border-radius: 20px;
  font-size: 0.8rem;
  font-weight: 600;
  border: 1px solid rgba(146, 20, 12, 0.2);
  transition: all 0.3s ease;
}

.tech-tag:hover {
  background: rgba(146, 20, 12, 0.25);
  border-color: var(--accent-mid);
  transform: translateY(-2px);
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

/* Responsive */
@media (max-width: 968px) {
  .projects-grid {
    grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
    gap: 2rem;
  }

  .project-image-wrapper {
    height: 240px;
  }
}

@media (max-width: 768px) {
  .projects {
    padding: 80px 1.5rem;
  }

  .projects-grid {
    grid-template-columns: 1fr;
    gap: 2rem;
  }

  .section-header {
    margin-bottom: 3rem;
  }

  .project-image-wrapper {
    height: 220px;
  }

  .project-content {
    padding: 1.5rem;
  }

  .overlay-content {
    flex-direction: column;
    gap: 1rem;
  }

  .project-link {
    width: 100%;
    justify-content: center;
  }
}

@media (max-width: 480px) {
  .project-number {
    font-size: 3rem;
    top: 1rem;
    right: 1rem;
  }

  .project-title {
    font-size: 1.3rem;
  }
}
</style>

