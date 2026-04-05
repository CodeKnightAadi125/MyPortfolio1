<template>
  <section id="contact" class="contact-section">
    <div class="contact-content">
      <h2 class="contact-title">Get In Touch</h2>
      <p class="contact-sub">
        I'm always open to new opportunities, collaborations, or just a friendly chat.
        Drop a message and I'll get back to you!
      </p>

      <div class="contact-body">
        <form class="contact-form" @submit.prevent="handleSubmit">
          <div class="form-group">
            <label for="name">Name</label>
            <input id="name" v-model="form.name" type="text" placeholder="Your name" required />
          </div>
          <div class="form-group">
            <label for="email">Email</label>
            <input id="email" v-model="form.email" type="email" placeholder="your@email.com" required />
          </div>
          <div class="form-group">
            <label for="message">Message</label>
            <textarea id="message" v-model="form.message" rows="5" placeholder="What's on your mind?" required></textarea>
          </div>
          <button type="submit" class="btn-submit" :disabled="submitted">
            {{ submitted ? '✅ Message Sent!' : 'Send Message →' }}
          </button>
        </form>

        <div class="social-panel">
          <p class="social-heading">Or reach me directly</p>

          <a class="social-card" href="https://github.com/CodeKnightAadi125" target="_blank">
            <svg class="social-icon" viewBox="0 0 24 24" fill="currentColor">
              <path d="M12 0C5.37 0 0 5.37 0 12c0 5.3 3.438 9.8 8.205 11.385.6.113.82-.258.82-.577 0-.285-.01-1.04-.015-2.04-3.338.724-4.042-1.61-4.042-1.61-.546-1.385-1.335-1.755-1.335-1.755-1.087-.744.084-.729.084-.729 1.205.084 1.838 1.236 1.838 1.236 1.07 1.835 2.809 1.305 3.495.998.108-.776.417-1.305.76-1.605-2.665-.3-5.466-1.332-5.466-5.93 0-1.31.465-2.38 1.235-3.22-.135-.303-.54-1.523.105-3.176 0 0 1.005-.322 3.3 1.23.96-.267 1.98-.399 3-.405 1.02.006 2.04.138 3 .405 2.28-1.552 3.285-1.23 3.285-1.23.645 1.653.24 2.873.12 3.176.765.84 1.23 1.91 1.23 3.22 0 4.61-2.805 5.625-5.475 5.92.42.36.81 1.096.81 2.22 0 1.605-.015 2.896-.015 3.286 0 .315.21.69.825.57C20.565 21.795 24 17.295 24 12c0-6.63-5.37-12-12-12z"/>
            </svg>
            <div class="social-text">
              <span class="social-label">GitHub</span>
              <span class="social-handle">github.com/CodeKnightAadi125</span>
            </div>
            <span class="social-arrow">→</span>
          </a>

          <a class="social-card" href="https://www.linkedin.com/in/aditya-ranjan-singh-10563831a/" target="_blank">
            <svg class="social-icon" viewBox="0 0 24 24" fill="currentColor">
              <path d="M20.447 20.452h-3.554v-5.569c0-1.328-.027-3.037-1.852-3.037-1.853 0-2.136 1.445-2.136 2.939v5.667H9.351V9h3.414v1.561h.046c.477-.9 1.637-1.85 3.37-1.85 3.601 0 4.267 2.37 4.267 5.455v6.286zM5.337 7.433a2.062 2.062 0 01-2.063-2.065 2.064 2.064 0 112.063 2.065zm1.782 13.019H3.555V9h3.564v11.452zM22.225 0H1.771C.792 0 0 .774 0 1.729v20.542C0 23.227.792 24 1.771 24h20.451C23.2 24 24 23.227 24 22.271V1.729C24 .774 23.2 0 22.222 0h.003z"/>
            </svg>
            <div class="social-text">
              <span class="social-label">LinkedIn</span>
              <span class="social-handle">linkedin.com/in/aditya-ranjan-singh-10563831a</span>
            </div>
            <span class="social-arrow">→</span>
          </a>

          <a class="social-card" href="mailto:adityasinghrajput0770@gmail.com">
            <svg class="social-icon" viewBox="0 0 24 24" fill="currentColor">
              <path d="M24 5.457v13.909c0 .904-.732 1.636-1.636 1.636h-3.819V11.73L12 16.64l-6.545-4.91v9.273H1.636A1.636 1.636 0 010 19.366V5.457c0-.904.732-1.636 1.636-1.636h.749L12 10.09l9.615-6.269h.749A1.636 1.636 0 0124 5.457z"/>
            </svg>
            <div class="social-text">
              <span class="social-label">Email</span>
              <span class="social-handle">adityasinghrajput0770@gmail.com</span>
            </div>
            <span class="social-arrow">→</span>
          </a>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
import { ref } from 'vue'

const form = ref({ name: '', email: '', message: '' })
const submitted = ref(false)

const handleSubmit = () => {
  console.log('Form submitted:', form.value)
  submitted.value = true
  setTimeout(() => {
    submitted.value = false
    form.value = { name: '', email: '', message: '' }
  }, 3000)
}
</script>

<style scoped>
.contact-section {
  background: linear-gradient(160deg, #ffffff 0%, #fff3ec 60%, #ffe8d6 100%);
  padding: 5rem 2rem;
}

.contact-content {
  max-width: 900px;
  margin: 0 auto;
  text-align: center;
}

.contact-title {
  font-size: 2.5rem;
  font-weight: 700;
  color: #1c1209;
  display: inline-block;
  margin-bottom: 0.5rem;
}

.contact-title::after {
  content: '';
  display: block;
  width: 50px;
  height: 3px;
  background: #ee5711;
  margin: 0.5rem auto 1rem;
  border-radius: 2px;
}

.contact-sub {
  font-size: 1rem;
  color: #78716c;
  line-height: 1.7;
  max-width: 540px;
  margin: 0 auto 2.5rem;
}

.contact-body {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 2.5rem;
  text-align: left;
}

.contact-form {
  display: flex;
  flex-direction: column;
  gap: 1.2rem;
}

.form-group {
  display: flex;
  flex-direction: column;
  gap: 0.4rem;
}

.form-group label {
  font-size: 0.85rem;
  font-weight: 600;
  color: #1e293b;
  letter-spacing: 0.03em;
}

.form-group input,
.form-group textarea {
  padding: 0.7rem 1rem;
  border: 1.5px solid #e2d5cc;
  border-radius: 10px;
  font-size: 0.95rem;
  color: #1c1209;
  background: #ffffff;
  outline: none;
  transition: border-color 0.25s;
  resize: none;
  font-family: inherit;
}

.form-group input::placeholder,
.form-group textarea::placeholder { color: #c4b8b0; }

.form-group input:focus,
.form-group textarea:focus { border-color: #ee5711; }

.btn-submit {
  padding: 0.8rem 2rem;
  background: #ee5711;
  color: white;
  border: none;
  border-radius: 10px;
  font-size: 1rem;
  font-weight: 600;
  cursor: pointer;
  transition: background 0.25s, transform 0.2s;
  align-self: flex-start;
}

.btn-submit:hover:not(:disabled) {
  background: #d44e0f;
  transform: translateY(-2px);
}

.btn-submit:disabled {
  background: #a3a3a3;
  cursor: default;
}

.social-panel {
  display: flex;
  flex-direction: column;
  gap: 1rem;
  justify-content: center;
}

.social-heading {
  font-size: 0.85rem;
  font-weight: 600;
  color: #a8a29e;
  text-transform: uppercase;
  letter-spacing: 0.08em;
  margin-bottom: 0.3rem;
}

.social-card {
  display: flex;
  align-items: center;
  gap: 1rem;
  padding: 1rem 1.2rem;
  background: #ffffff;
  border: 1px solid #f0e8e0;
  border-radius: 12px;
  text-decoration: none;
  transition: border-color 0.25s, transform 0.25s;
}

.social-card:hover {
  border-color: #ee5711;
  transform: translateX(4px);
}

.social-icon {
  width: 26px;
  height: 26px;
  color: #ee5711;
  flex-shrink: 0;
}

.social-text {
  display: flex;
  flex-direction: column;
  flex: 1;
}

.social-label {
  font-size: 0.95rem;
  font-weight: 700;
  color: #1c1209;
}

.social-handle {
  font-size: 0.8rem;
  color: #a8a29e;
}

.social-arrow {
  font-size: 1rem;
  color: #ee5711;
  font-weight: 700;
}

@media (max-width: 640px) {
  .contact-body { grid-template-columns: 1fr; }
  .btn-submit { align-self: stretch; text-align: center; }
}
</style>