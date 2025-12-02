<template>
  <section id="projects" class="projects">
    <div class="container">
      <h2 class="section-title">
        <span class="title-number">03.</span>
        Personal Projects
      </h2>
      <div class="projects-grid">
        <div
          v-for="project in projects"
          :key="project.id"
          class="project-card"
        >
          <div class="project-image">
  <img
    v-if="project.image"
    :src="project.image"
    alt="Project Image"
    class="img-fill"
  />
  <div v-else class="image-placeholder">
    <span>Project Image</span>
  </div>
            <div class="project-overlay">
              <a
                :href="project.github"
                target="_blank"
                class="project-link"
                title="View on GitHub"
              >
                <svg viewBox="0 0 24 24" fill="currentColor">
                  <path d="M12 0c-6.626 0-12 5.373-12 12 0 5.302 3.438 9.8 8.207 11.387.599.111.793-.261.793-.577v-2.234c-3.338.726-4.033-1.416-4.033-1.416-.546-1.387-1.333-1.756-1.333-1.756-1.089-.745.083-.729.083-.729 1.205.084 1.839 1.237 1.839 1.237 1.07 1.834 2.807 1.304 3.492.997.107-.775.418-1.305.762-1.604-2.665-.305-5.467-1.334-5.467-5.931 0-1.311.469-2.381 1.236-3.221-.124-.303-.535-1.524.117-3.176 0 0 1.008-.322 3.301 1.23.957-.266 1.983-.399 3.003-.404 1.02.005 2.047.138 3.006.404 2.291-1.552 3.297-1.23 3.297-1.23.653 1.653.242 2.874.118 3.176.77.84 1.235 1.911 1.235 3.221 0 4.609-2.807 5.624-5.479 5.921.43.372.823 1.102.823 2.222v3.293c0 .319.192.694.801.576 4.765-1.589 8.199-6.086 8.199-11.386 0-6.627-5.373-12-12-12z"/>
                </svg>
              </a>
              <a
                v-if="project.live"
                :href="project.live"
                target="_blank"
                class="project-link"
                title="View Live"
              >
                <svg viewBox="0 0 24 24" fill="currentColor">
                  <path d="M12 0c-6.627 0-12 5.373-12 12s5.373 12 12 12 12-5.373 12-12-5.373-12-12-12zm1 16h-2v-6h2v6zm0-8h-2v-2h2v2z"/>
                </svg>
              </a>
            </div>
          </div>
          <div class="project-content">
            <h3 class="project-title">{{ project.title }}</h3>
            <p class="project-description">{{ project.description }}</p>
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
  padding: 100px 2rem;
  background: linear-gradient(135deg, #1E1E24 0%, #2A2A35 45%, #353540 100%);
  min-height: 100vh;
  width: 100%;
  box-sizing: border-box;
  overflow-x: hidden;
}

.container {
  max-width: 1200px;
  margin: 0 auto;
}

.section-title {
  font-size: 2.5rem;
  color: #FFF8F0;
  margin-bottom: 3rem;
  display: flex;
  align-items: center;
  gap: 1rem;
  font-weight: 700;
}

.title-number {
  color: #92140C;
  font-family: 'Courier New', monospace;
  font-size: 1.5rem;
}

.projects-grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(350px, 1fr));
  gap: 2rem;
}

.project-card {
  background: #2A2A35;
  border-radius: 12px;
  overflow: hidden;
  transition: transform 0.3s ease, box-shadow 0.3s ease;
  border: 1px solid rgba(146, 20, 12, 0.2);
}

.project-card:hover {
  transform: translateY(-10px);
  box-shadow: 0 20px 40px rgba(146, 20, 12, 0.35);
  border-color: #92140C;
}

.project-image {
  position: relative;
  width: 100%;
  height: 250px;
  overflow: hidden;
  background: linear-gradient(135deg, #92140C 0%, #6E100A 100%);
}

.image-placeholder {
  width: 100%;
  height: 100%;
  display: flex;
  align-items: center;
  justify-content: center;
  color: rgba(255, 248, 240, 0.8);
  font-size: 1.2rem;
  background: rgba(0, 0, 0, 0.3);
}

.project-overlay {
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background: rgba(0, 0, 0, 0.8);
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 2rem;
  opacity: 0;
  transition: opacity 0.3s ease;
}

.project-card:hover .project-overlay {
  opacity: 1;
}

.project-link {
  color: #FFF8F0;
  width: 50px;
  height: 50px;
  display: flex;
  align-items: center;
  justify-content: center;
  border-radius: 50%;
  background: rgba(146, 20, 12, 0.3);
  transition: all 0.3s ease;
}

.project-link:hover {
  background: #92140C;
  transform: scale(1.1);
}

.project-link svg {
  width: 24px;
  height: 24px;
}

.project-content {
  padding: 1.5rem;
}

.project-title {
  font-size: 1.5rem;
  color: #FFF8F0;
  margin: 0 0 1rem;
  font-weight: 600;
}

.project-description {
  color: #b3a093;
  line-height: 1.6;
  margin-bottom: 1.5rem;
  font-size: 0.95rem;
}

.project-tech {
  display: flex;
  flex-wrap: wrap;
  gap: 0.5rem;
}

.tech-tag {
  padding: 0.3rem 0.8rem;
  background: rgba(146, 20, 12, 0.2);
  color: #92140C;
  border-radius: 4px;
  font-size: 0.85rem;
  font-weight: 500;
}
.img-fill {
  width: 100%;
  height: 100%;
  object-fit: cover;
  display: block;
}


@media (max-width: 768px) {
  .projects-grid {
    grid-template-columns: 1fr;
  }

  .project-image {
    height: 200px;
  }
}
</style>

