<script setup lang="ts">
import { ref } from 'vue'
import { RouterLink } from 'vue-router'

const email = ref('')
const subscribeMessage = ref('')

const handleNewsletterSubmit = () => {
  if (email.value) {
    subscribeMessage.value = 'Thank you for subscribing!'
    email.value = ''
    setTimeout(() => {
      subscribeMessage.value = ''
    }, 3000)
  }
}
</script>

<template>
  <footer class="footer">
    <div class="footer-container">
      <!-- Logo and Company Info Section -->
      <div class="footer-section company-section">
        <div class="footer-logo">
          <img alt="NGO Logo" src="@/assets/logo.svg" class="logo-img" />
        </div>
        <p class="company-description">
          NGO is dedicated to creating positive change
          and improving lives through compassionate action and sustainable development initiatives.
        </p>
        <div class="social-links">
          <a href="#" class="social-icon" title="Facebook">f</a>
          <a href="#" class="social-icon" title="Twitter">𝕏</a>
          <a href="#" class="social-icon" title="LinkedIn">in</a>
          <a href="#" class="social-icon" title="Instagram">@</a>
        </div>
      </div>

      <!-- Quick Links Section -->
      <div class="footer-section">
        <h3 class="footer-heading">Quick Links</h3>
        <ul class="footer-menu">
          <li><RouterLink to="/">Home</RouterLink></li>
          <li><RouterLink to="/about">About Us</RouterLink></li>
          <li><RouterLink to="/services">Our Services</RouterLink></li>
          <li><RouterLink to="/contact">Contact Us</RouterLink></li>
        </ul>
      </div>

      <!-- Services Section -->
      <div class="footer-section">
        <h3 class="footer-heading">Services</h3>
        <ul class="footer-menu">
          <li><a href="#community">Community Development</a></li>
          <li><a href="#education">Education Programs</a></li>
          <li><a href="#healthcare">Healthcare Initiatives</a></li>
          <li><a href="#environment">Environmental Projects</a></li>
        </ul>
      </div>

      <!-- Newsletter Section -->
      <div class="footer-section newsletter-section">
        <h3 class="footer-heading">Newsletter</h3>
        <p class="newsletter-description">
          Subscribe to stay updated with our latest news and initiatives.
        </p>
        <form @submit.prevent="handleNewsletterSubmit" class="newsletter-form">
          <input
            v-model="email"
            type="email"
            placeholder="Enter your email"
            class="newsletter-input"
            required
          />
          <button type="submit" class="newsletter-button">Subscribe</button>
        </form>
        <div v-if="subscribeMessage" class="subscribe-message">{{ subscribeMessage }}</div>
      </div>
    </div>

    <!-- Copyright Section -->
    <div class="footer-bottom">
      <div class="footer-bottom-content">
        <p class="copyright">
          &copy; {{ new Date().getFullYear() }} NGO. All
          rights reserved.
        </p>
        <div class="footer-links">
          <a href="#privacy">Privacy Policy</a>
          <span class="divider">•</span>
          <a href="#terms">Terms of Service</a>
          <span class="divider">•</span>
          <a href="#cookies">Cookie Policy</a>
        </div>
      </div>
    </div>
  </footer>
</template>

<style scoped>
.footer {
  background: linear-gradient(135deg, #1e293b 0%, #0f172a 100%);
  color: #e2e8f0;
  margin-top: 4rem;
}

.footer-container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 3rem 2rem;
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
  gap: 2rem;
}

.footer-section {
  display: flex;
  flex-direction: column;
}

.company-section {
  gap: 1.5rem;
}

.footer-logo {
  display: flex;
  align-items: center;
}

.logo-img {
  height: 50px;
  width: auto;
}

.company-description {
  font-size: 0.95rem;
  line-height: 1.6;
  color: #cbd5e1;
}

.social-links {
  display: flex;
  gap: 1rem;
  margin-top: 1rem;
}

.social-icon {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  width: 40px;
  height: 40px;
  background-color: rgba(148, 163, 184, 0.2);
  border-radius: 50%;
  color: #e2e8f0;
  text-decoration: none;
  font-weight: 600;
  transition: all 0.3s ease;
}

.social-icon:hover {
  background-color: #42b983;
  color: #fff;
  transform: translateY(-3px);
}

.footer-heading {
  font-size: 1.1rem;
  font-weight: 600;
  margin-bottom: 1.5rem;
  color: #f1f5f9;
}

.footer-menu {
  list-style: none;
  padding: 0;
  display: flex;
  flex-direction: column;
  gap: 0.75rem;
}

.footer-menu a {
  color: #cbd5e1;
  text-decoration: none;
  transition: all 0.3s ease;
  display: inline-block;
}

.footer-menu a:hover {
  color: #42b983;
  padding-left: 0.5rem;
}

.newsletter-section {
  gap: 1rem;
}

.newsletter-description {
  font-size: 0.95rem;
  color: #cbd5e1;
  line-height: 1.6;
}

.newsletter-form {
  display: flex;
  flex-direction: column;
  gap: 0.75rem;
}

.newsletter-input {
  padding: 0.75rem 1rem;
  border: 1px solid rgba(148, 163, 184, 0.3);
  border-radius: 4px;
  background-color: rgba(15, 23, 42, 0.5);
  color: #f1f5f9;
  font-size: 0.95rem;
  transition: all 0.3s ease;
}

.newsletter-input::placeholder {
  color: #94a3b8;
}

.newsletter-input:focus {
  outline: none;
  border-color: #42b983;
  background-color: rgba(15, 23, 42, 0.7);
  box-shadow: 0 0 0 3px rgba(66, 185, 131, 0.1);
}

.newsletter-button {
  padding: 0.75rem 1.5rem;
  background-color: #42b983;
  color: #fff;
  border: none;
  border-radius: 4px;
  font-weight: 600;
  cursor: pointer;
  transition: all 0.3s ease;
  font-size: 0.95rem;
}

.newsletter-button:hover {
  background-color: #359268;
  transform: translateY(-2px);
  box-shadow: 0 4px 12px rgba(66, 185, 131, 0.3);
}

.newsletter-button:active {
  transform: translateY(0);
}

.subscribe-message {
  color: #86efac;
  font-size: 0.9rem;
  padding: 0.75rem 1rem;
  background-color: rgba(134, 239, 172, 0.1);
  border-left: 3px solid #86efac;
  border-radius: 4px;
}

.footer-bottom {
  background-color: rgba(0, 0, 0, 0.3);
  border-top: 1px solid rgba(148, 163, 184, 0.2);
  padding: 1.5rem 2rem;
}

.footer-bottom-content {
  max-width: 1200px;
  margin: 0 auto;
  display: flex;
  flex-direction: column;
  gap: 1rem;
  align-items: center;
  text-align: center;
}

.copyright {
  margin: 0;
  font-size: 0.9rem;
  color: #94a3b8;
}

.footer-links {
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 0.75rem;
  flex-wrap: wrap;
  font-size: 0.9rem;
}

.footer-links a {
  color: #cbd5e1;
  text-decoration: none;
  transition: color 0.3s ease;
}

.footer-links a:hover {
  color: #42b983;
}

.divider {
  color: #64748b;
}

/* Responsive Design */
@media (max-width: 768px) {
  .footer-container {
    grid-template-columns: 1fr;
    padding: 2rem 1.5rem;
    gap: 1.5rem;
  }

  .footer-bottom-content {
    flex-direction: column;
  }

  .copyright {
    font-size: 0.85rem;
  }

  .footer-links {
    font-size: 0.85rem;
    gap: 0.5rem;
  }
}

@media (max-width: 480px) {
  .footer-container {
    padding: 1.5rem 1rem;
    gap: 1rem;
  }

  .footer-heading {
    font-size: 1rem;
    margin-bottom: 1rem;
  }

  .footer-menu {
    gap: 0.5rem;
  }

  .company-description {
    font-size: 0.9rem;
  }

  .newsletter-description {
    font-size: 0.9rem;
  }

  .newsletter-input,
  .newsletter-button {
    font-size: 0.9rem;
  }

  .social-icon {
    width: 35px;
    height: 35px;
    font-size: 0.9rem;
  }
}
</style>
