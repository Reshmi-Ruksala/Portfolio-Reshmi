<template>
  <section id="contact" class="contact">
    <div class="container">
      <div class="section-header">
        <span class="section-label">Get In Touch</span>
        <h2 class="section-title">
          Let's <span class="title-accent">Connect</span>
        </h2>
        <p class="section-subtitle">
          Have a project in mind or want to collaborate? I'd love to hear from you. 
          Send me a message and I'll respond as soon as possible.
        </p>
      </div>

      <div class="contact-content">
        <div class="contact-info">
          <div class="info-card">
            <div class="info-icon">
              <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                <path d="M21 10c0 7-9 13-9 13s-9-6-9-13a9 9 0 0 1 18 0z"/>
                <circle cx="12" cy="10" r="3"/>
              </svg>
            </div>
            <h3 class="info-title">Location</h3>
            <p class="info-text">Sri Lanka</p>
          </div>

          <div class="info-card">
            <div class="info-icon">
              <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                <path d="M4 4h16c1.1 0 2 .9 2 2v12c0 1.1-.9 2-2 2H4c-1.1 0-2-.9-2-2V6c0-1.1.9-2 2-2z"/>
                <polyline points="22,6 12,13 2,6"/>
              </svg>
            </div>
            <h3 class="info-title">Email</h3>
            <a href="mailto:reshmivithanage.com" class="info-link">reshmivithanage.com</a>
          </div>

          <div class="contact-social">
            <span class="social-label">Follow Me</span>
            <div class="social-links">
              <a href="https://www.linkedin.com/in/reshmi-ruksala-44b847326/" target="_blank" class="social-link" title="LinkedIn">
                <svg viewBox="0 0 24 24" fill="currentColor">
                  <path d="M19 0h-14c-2.761 0-5 2.239-5 5v14c0 2.761 2.239 5 5 5h14c2.762 0 5-2.239 5-5v-14c0-2.761-2.238-5-5-5zm-11 19h-3v-11h3v11zm-1.5-12.268c-.966 0-1.75-.79-1.75-1.764s.784-1.764 1.75-1.764 1.75.79 1.75 1.764-.783 1.764-1.75 1.764zm13.5 12.268h-3v-5.604c0-3.368-4-3.113-4 0v5.604h-3v-11h3v1.765c1.396-2.586 7-2.777 7 2.476v6.759z"/>
                </svg>
              </a>
              <a href="https://github.com/Reshmi-Ruksala" target="_blank" class="social-link" title="GitHub">
                <svg viewBox="0 0 24 24" fill="currentColor">
                  <path d="M12 0c-6.626 0-12 5.373-12 12 0 5.302 3.438 9.8 8.207 11.387.599.111.793-.261.793-.577v-2.234c-3.338.726-4.033-1.416-4.033-1.416-.546-1.387-1.333-1.756-1.333-1.756-1.089-.745.083-.729.083-.729 1.205.084 1.839 1.237 1.839 1.237 1.07 1.834 2.807 1.304 3.492.997.107-.775.418-1.305.762-1.604-2.665-.305-5.467-1.334-5.467-5.931 0-1.311.469-2.381 1.236-3.221-.124-.303-.535-1.524.117-3.176 0 0 1.008-.322 3.301 1.23.957-.266 1.983-.399 3.003-.404 1.02.005 2.047.138 3.006.404 2.291-1.552 3.297-1.23 3.297-1.23.653 1.653.242 2.874.118 3.176.77.84 1.235 1.911 1.235 3.221 0 4.609-2.807 5.624-5.479 5.921.43.372.823 1.102.823 2.222v3.293c0 .319.192.694.801.576 4.765-1.589 8.199-6.086 8.199-11.386 0-6.627-5.373-12-12-12z"/>
                </svg>
              </a>
            </div>
          </div>
        </div>

        <form class="contact-form" @submit.prevent="handleSubmit">
          <div class="form-header">
            <h3 class="form-title">Send a Message</h3>
            <p class="form-subtitle">Fill out the form below and I'll get back to you</p>
          </div>

          <div class="form-row">
            <div class="form-group">
              <label for="name">
                <span>Name</span>
                <span class="required">*</span>
              </label>
              <input
                id="name"
                v-model="form.name"
                type="text"
                required
                placeholder="John Doe"
              />
            </div>
            <div class="form-group">
              <label for="email">
                <span>Email</span>
                <span class="required">*</span>
              </label>
              <input
                id="email"
                v-model="form.email"
                type="email"
                required
                placeholder="john@example.com"
              />
            </div>
          </div>

          <div class="form-group">
            <label for="subject">
              <span>Subject</span>
              <span class="required">*</span>
            </label>
            <input
              id="subject"
              v-model="form.subject"
              type="text"
              required
              placeholder="Project Inquiry"
            />
          </div>

          <div class="form-group">
            <label for="message">
              <span>Message</span>
              <span class="required">*</span>
            </label>
            <textarea
              id="message"
              v-model="form.message"
              required
              rows="6"
              placeholder="Tell me about your project..."
            ></textarea>
          </div>

          <div class="form-footer">
            <button type="submit" class="submit-btn" :disabled="isSubmitting">
              <span v-if="!isSubmitting">Send Message</span>
              <span v-else class="loading">
                <span class="spinner"></span>
                Sending...
              </span>
            </button>
            <div v-if="submitStatus === 'success'" class="status-message success">
              <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                <polyline points="20 6 9 17 4 12"/>
              </svg>
              Message sent successfully!
            </div>
            <div v-if="submitStatus === 'error'" class="status-message error">
              <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                <circle cx="12" cy="12" r="10"/>
                <line x1="12" y1="8" x2="12" y2="12"/>
                <line x1="12" y1="16" x2="12.01" y2="16"/>
              </svg>
              Something went wrong. Please try again.
            </div>
          </div>
        </form>
      </div>
    </div>
  </section>
</template>

<script setup lang="ts">
import { ref, reactive } from 'vue'

const isSubmitting = ref(false)
const submitStatus = ref<'success' | 'error' | null>(null)

const form = reactive({
  name: '',
  email: '',
  subject: '',
  message: ''
})

const handleSubmit = async () => {
  isSubmitting.value = true
  submitStatus.value = null

  try {
    const response = await fetch('https://formspree.io/f/xzznnjan', {
      method: 'POST',
      headers: {
        'Content-Type': 'application/json',
      },
      body: JSON.stringify({
        name: form.name,
        email: form.email,
        subject: form.subject,
        message: form.message,
        _replyto: form.email // Important for reply-to functionality
      })
    })

    if (response.ok) {
      submitStatus.value = 'success'
      // Reset form
      form.name = ''
      form.email = ''
      form.subject = ''
      form.message = ''
    } else {
      throw new Error('Form submission failed')
    }
  } catch (error) {
    submitStatus.value = 'error'
    console.error('Error submitting form:', error)
  } finally {
    isSubmitting.value = false
  }
}
</script>

<style scoped>
.contact {
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

.contact::before {
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
  max-width: 700px;
  margin: 0 auto;
  line-height: 1.6;
}

/* Contact Content */
.contact-content {
  display: grid;
  grid-template-columns: 1fr 1.2fr;
  gap: 4rem;
  align-items: start;
}

/* Contact Info */
.contact-info {
  display: flex;
  flex-direction: column;
  gap: 2rem;
  animation: fadeInLeft 0.8s ease;
}

.info-card {
  background: rgba(42, 42, 53, 0.4);
  backdrop-filter: blur(10px);
  border: 1px solid rgba(146, 20, 12, 0.1);
  border-radius: 20px;
  padding: 2rem;
  transition: all 0.4s ease;
}

.info-card:hover {
  transform: translateY(-5px);
  border-color: rgba(146, 20, 12, 0.3);
  box-shadow: 0 15px 35px rgba(146, 20, 12, 0.15);
}

.info-icon {
  width: 50px;
  height: 50px;
  background: rgba(146, 20, 12, 0.15);
  border-radius: 12px;
  display: flex;
  align-items: center;
  justify-content: center;
  color: var(--accent-mid);
  margin-bottom: 1rem;
}

.info-icon svg {
  width: 24px;
  height: 24px;
}

.info-title {
  font-size: 1rem;
  color: var(--text-muted);
  margin: 0 0 0.5rem;
  font-weight: 600;
  text-transform: uppercase;
  letter-spacing: 1px;
  font-size: 0.85rem;
}

.info-text {
  font-size: 1.1rem;
  color: var(--color-text-light);
  margin: 0;
  font-weight: 500;
}

.info-link {
  font-size: 1.1rem;
  color: var(--accent-mid);
  text-decoration: none;
  font-weight: 500;
  transition: all 0.3s ease;
  display: inline-block;
}

.info-link:hover {
  color: var(--color-text-light);
  transform: translateX(5px);
}

.contact-social {
  background: rgba(42, 42, 53, 0.4);
  backdrop-filter: blur(10px);
  border: 1px solid rgba(146, 20, 12, 0.1);
  border-radius: 20px;
  padding: 2rem;
}

.social-label {
  display: block;
  font-size: 0.85rem;
  color: var(--text-muted);
  text-transform: uppercase;
  letter-spacing: 1px;
  margin-bottom: 1rem;
  font-weight: 600;
}

.social-links {
  display: flex;
  gap: 1rem;
}

.social-link {
  width: 50px;
  height: 50px;
  background: rgba(146, 20, 12, 0.15);
  border: 1px solid rgba(146, 20, 12, 0.2);
  border-radius: 12px;
  display: flex;
  align-items: center;
  justify-content: center;
  color: var(--accent-mid);
  text-decoration: none;
  transition: all 0.3s ease;
}

.social-link:hover {
  background: var(--accent-mid);
  color: var(--color-text-light);
  transform: translateY(-3px);
  box-shadow: 0 8px 20px rgba(146, 20, 12, 0.4);
}

.social-link svg {
  width: 22px;
  height: 22px;
}

/* Contact Form */
.contact-form {
  background: rgba(42, 42, 53, 0.4);
  backdrop-filter: blur(10px);
  border: 1px solid rgba(146, 20, 12, 0.1);
  border-radius: 20px;
  padding: 2.5rem;
  animation: fadeInRight 0.8s ease;
}

.form-header {
  margin-bottom: 2rem;
}

.form-title {
  font-size: 1.8rem;
  color: var(--color-text-light);
  margin: 0 0 0.5rem;
  font-weight: 700;
}

.form-subtitle {
  font-size: 0.95rem;
  color: var(--text-muted);
  margin: 0;
}

.form-row {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 1.5rem;
}

.form-group {
  display: flex;
  flex-direction: column;
  gap: 0.6rem;
  margin-bottom: 1.5rem;
}

.form-group label {
  display: flex;
  align-items: center;
  gap: 0.3rem;
  color: var(--color-text-light);
  font-weight: 600;
  font-size: 0.9rem;
}

.required {
  color: var(--accent-mid);
}

.form-group input,
.form-group textarea {
  padding: 1rem 1.2rem;
  border: 1px solid rgba(146, 20, 12, 0.2);
  border-radius: 12px;
  background: rgba(30, 30, 36, 0.5);
  color: var(--color-text-light);
  font-size: 1rem;
  font-family: inherit;
  transition: all 0.3s ease;
  width: 100%;
  box-sizing: border-box;
}

.form-group input:focus,
.form-group textarea:focus {
  outline: none;
  border-color: var(--accent-mid);
  background: rgba(30, 30, 36, 0.7);
  box-shadow: 0 0 0 3px rgba(146, 20, 12, 0.1);
}

.form-group input::placeholder,
.form-group textarea::placeholder {
  color: var(--text-muted);
}

.form-group textarea {
  resize: vertical;
  min-height: 140px;
  font-family: inherit;
}

.form-footer {
  margin-top: 1rem;
}

.submit-btn {
  padding: 1.1rem 2.5rem;
  background: linear-gradient(135deg, var(--accent-mid) 0%, #6E100A 100%);
  color: var(--color-text-light);
  border: none;
  border-radius: 12px;
  font-size: 1rem;
  font-weight: 600;
  cursor: pointer;
  transition: all 0.3s ease;
  display: flex;
  align-items: center;
  gap: 0.5rem;
  position: relative;
  overflow: hidden;
}

.submit-btn::before {
  content: '';
  position: absolute;
  top: 0;
  left: -100%;
  width: 100%;
  height: 100%;
  background: linear-gradient(90deg, transparent, rgba(255, 248, 240, 0.2), transparent);
  transition: left 0.5s ease;
}

.submit-btn:hover:not(:disabled)::before {
  left: 100%;
}

.submit-btn:hover:not(:disabled) {
  transform: translateY(-2px);
  box-shadow: 0 10px 30px rgba(146, 20, 12, 0.4);
}

.submit-btn:disabled {
  opacity: 0.6;
  cursor: not-allowed;
}

.loading {
  display: flex;
  align-items: center;
  gap: 0.5rem;
}

.spinner {
  width: 16px;
  height: 16px;
  border: 2px solid rgba(255, 248, 240, 0.3);
  border-top-color: var(--color-text-light);
  border-radius: 50%;
  animation: spin 0.8s linear infinite;
}

.status-message {
  margin-top: 1rem;
  padding: 1rem;
  border-radius: 12px;
  display: flex;
  align-items: center;
  gap: 0.75rem;
  font-size: 0.9rem;
  font-weight: 500;
  animation: slideDown 0.3s ease;
}

.status-message svg {
  width: 20px;
  height: 20px;
  flex-shrink: 0;
}

.status-message.success {
  background: rgba(34, 197, 94, 0.1);
  color: #22c55e;
  border: 1px solid rgba(34, 197, 94, 0.2);
}

.status-message.error {
  background: rgba(239, 68, 68, 0.1);
  color: #ef4444;
  border: 1px solid rgba(239, 68, 68, 0.2);
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

@keyframes spin {
  to {
    transform: rotate(360deg);
  }
}

@keyframes slideDown {
  from {
    opacity: 0;
    transform: translateY(-10px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

/* Responsive */
@media (max-width: 968px) {
  .contact-content {
    grid-template-columns: 1fr;
    gap: 3rem;
  }

  .form-row {
    grid-template-columns: 1fr;
  }

  .contact-form {
    padding: 2rem;
  }
}

@media (max-width: 768px) {
  .contact {
    padding: 80px 1.5rem;
  }

  .section-header {
    margin-bottom: 3rem;
  }

  .info-card,
  .contact-social {
    padding: 1.5rem;
  }
}

@media (max-width: 480px) {
  .contact-form {
    padding: 1.5rem;
  }

  .form-title {
    font-size: 1.5rem;
  }
}
</style>

