<template>
  <section id="about" class="about">
    <div class="container">
      <h2 class="section-title">
        <span class="title-number">01.</span>
        About Me
      </h2>
      <div class="about-content">
        <div class="about-text">
          <p>
            I'm Binada Pasandul, an IT undergraduate at SLIIT and a dedicated full-stack developer with strong expertise in backend development, cloud computing, and scalable 
            system architecture. Over the past few years, I’ve completed 6+ full-stack projects across MERN, Java JSP/Servlet, PHP-MySQL, and Android, gaining hands-on experience building secure APIs, 
            real-time applications, and production-ready platforms. 
            I’ve worked with international clients, including delivering a real-time trading project integrating React, C#, SignalR, and WebSockets using Agile and Jira.
          </p>
          <p>
            I’m skilled in technologies such as Java, JavaScript, Python, C#, React.js, Node.js, SQL, MongoDB, AWS, Azure, and 
            .NET — and I enjoy turning complex requirements into clean, efficient, and well-designed systems. Beyond development, I value continuous
             learning, problem-solving, and writing maintainable code that scales. My goal is to grow as a backend and cloud engineer while creating high-quality digital solutions
             that make a real impact.
          </p>
          <p>Here are a few technologies I've been working with recently:</p>
          <ul class="tech-list">
            <li>MERN</li>
            <li>TypeScript</li>
            <li>Python</li>
            <li>Vue.js</li>
            <li>.NET</li>
            <li>Angular</li>
            <li>C#</li>
            <li>Git & GitHub</li>
            <li>RESTful APIs</li>
            <li>Jira</li>
          </ul>
        </div>
        <div class="about-image">
          <div class="image-wrapper">
            <div class="image-border"></div>
            <div class="image-content">
              <img :src="binadaPic" alt="Binada Pasandul" class="about-profile-image" />
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup lang="ts">
import binadaPic from '../assets/binada.jpeg'
</script>

<style scoped>
.about {
  padding: 100px 2rem;
  background: #0f0c29;
  min-height: 100vh;
  display: flex;
  align-items: center;
}

.container {
  max-width: 1200px;
  margin: 0 auto;
  width: 100%;
}

.section-title {
  font-size: 2.5rem;
  color: #fff;
  margin-bottom: 3rem;
  display: flex;
  align-items: center;
  gap: 1rem;
  font-weight: 700;
}

.title-number {
  color: #667eea;
  font-family: 'Courier New', monospace;
  font-size: 1.5rem;
}

.about-content {
  display: grid;
  grid-template-columns: 2fr 1fr;
  gap: 4rem;
  align-items: start;
}

.about-text {
  color: #d0d0d0;
  line-height: 1.8;
  font-size: 1.1rem;
}

.about-text p {
  margin-bottom: 1.5rem;
}

.tech-list {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  gap: 0.5rem;
  list-style: none;
  padding: 0;
  margin-top: 1rem;
}

.tech-list li {
  position: relative;
  padding-left: 1.5rem;
  color: #b0b0b0;
}

.tech-list li::before {
  content: '▹';
  position: absolute;
  left: 0;
  color: #667eea;
}

.about-image {
  display: flex;
  justify-content: center;
  align-items: center;
}

.image-wrapper {
  position: relative;
  width: 300px;
  height: 300px;
}

.image-border {
  position: absolute;
  top: 20px;
  left: 20px;
  width: 100%;
  height: 100%;
  border: 2px solid #667eea;
  border-radius: 4px;
  transition: transform 0.3s ease;
}

.image-wrapper:hover .image-border {
  transform: translate(-10px, -10px);
}

.image-content {
  position: relative;
  width: 100%;
  height: 100%;
  background: linear-gradient(135deg, #1a1a2e 0%, #16213e 100%);
  border-radius: 4px;
  overflow: hidden;
  z-index: 1;
}

.about-profile-image {
  width: 100%;
  height: 100%;
  object-fit: cover;
  border-radius: 4px;
}

.placeholder-content {
  width: 100%;
  height: 100%;
  display: flex;
  align-items: center;
  justify-content: center;
  color: #667eea;
  font-size: 1.2rem;
  background: rgba(102, 126, 234, 0.1);
}

@media (max-width: 968px) {
  .about-content {
    grid-template-columns: 1fr;
    gap: 3rem;
  }

  .about-image {
    order: -1;
  }

  .image-wrapper {
    width: 250px;
    height: 250px;
  }
}
</style>

