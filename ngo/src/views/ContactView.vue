<script setup lang="ts">
import { ref } from 'vue'

const formData = ref({
  name: '',
  email: '',
  phone: '',
  subject: '',
  message: '',
  service: ''
})

const submitStatus = ref<'idle' | 'submitting' | 'success' | 'error'>('idle')
const errorMessage = ref('')

const expandedFaqId = ref<number | null>(null)

const faqItems = [
  {
    id: 1,
    question: 'How can I volunteer with your organization?',
    answer: 'We welcome volunteers! Please fill out the contact form with "Volunteering Opportunities" selected, or email us at volunteer@whlif.org. We will provide information about available opportunities.'
  },
  {
    id: 2,
    question: 'How do I make a donation?',
    answer: 'You can make a donation through our website, contact us directly, or send a check to our office. Select "Donation Information" in the contact form for detailed payment options.'
  },
  {
    id: 3,
    question: 'How are donations used?',
    answer: 'We ensure 85% of donations go directly to program implementation. The remaining 15% covers administrative costs. Our detailed annual reports are available upon request.'
  },
  {
    id: 4,
    question: 'Can organizations partner with you?',
    answer: 'Yes! We actively seek partnerships with government agencies, NGOs, and corporate organizations. Select "Partnership Inquiry" in the contact form to discuss collaboration.'
  },
  {
    id: 5,
    question: 'How quickly will you respond?',
    answer: 'We aim to respond to all inquiries within 24 business hours. For urgent matters, please call our helpline number.'
  },
  {
    id: 6,
    question: 'Are you a registered NGO?',
    answer: 'Yes, we are a fully registered non-profit organization with all necessary legal certifications. Registration details are available upon request.'
  }
]

const toggleFaq = (id: number) => {
  expandedFaqId.value = expandedFaqId.value === id ? null : id
}

const handleSubmit = async (e: Event) => {
  const form = e.target as HTMLFormElement
  submitStatus.value = 'submitting'

  try {
    // Netlify will handle form submission automatically
    const formDataObj = new FormData(form)
    const response = await fetch('/', {
      method: 'POST',
      headers: { 'Content-Type': 'application/x-www-form-urlencoded' },
      body: new URLSearchParams(formDataObj as any).toString()
    })

    if (response.ok) {
      submitStatus.value = 'success'
      formData.value = {
        name: '',
        email: '',
        phone: '',
        subject: '',
        message: '',
        service: ''
      }
      setTimeout(() => {
        submitStatus.value = 'idle'
      }, 3000)
    } else {
      submitStatus.value = 'error'
      errorMessage.value = 'Failed to submit form. Please try again.'
    }
  } catch (error) {
    submitStatus.value = 'error'
    errorMessage.value = 'An error occurred. Please try again later.'
  }
}

const officeLocations = [
  {
    name: 'Head Office',
    address: '123 Foundation Street, City Center',
    phone: '+1 (555) 123-4567',
    email: 'info@whlif.org',
    hours: 'Mon - Fri: 9:00 AM - 5:00 PM'
  },
  {
    name: 'Community Center',
    address: '456 Community Avenue, Rural Area',
    phone: '+1 (555) 234-5678',
    email: 'community@whlif.org',
    hours: 'Mon - Sat: 8:00 AM - 6:00 PM'
  },
  {
    name: 'Helpline',
    address: 'Available nationwide',
    phone: '+1 (555) 999-8888',
    email: 'support@whlif.org',
    hours: 'Mon - Fri: 10:00 AM - 6:00 PM'
  }
]
</script>

<template>
  <div class="contact">
    <!-- Page Header -->
    <section class="page-header">
      <div class="header-content">
        <h1 class="header-title">Contact Us</h1>
        <p class="header-subtitle">We'd Love to Hear From You</p>
      </div>
    </section>

    <!-- Contact Information Cards -->
    <section class="info-section">
      <div class="info-container">
        <h2 class="section-title">Get In Touch</h2>

        <div class="info-grid">
          <div v-for="location in officeLocations" :key="location.name" class="info-card">
            <div class="info-icon">📍</div>
            <h3 class="info-title">{{ location.name }}</h3>
            <div class="info-detail">
              <span class="detail-label">Address:</span>
              <p>{{ location.address }}</p>
            </div>
            <div class="info-detail">
              <span class="detail-label">Phone:</span>
              <a :href="`tel:${location.phone}`" class="info-link">{{ location.phone }}</a>
            </div>
            <div class="info-detail">
              <span class="detail-label">Email:</span>
              <a :href="`mailto:${location.email}`" class="info-link">{{ location.email }}</a>
            </div>
            <div class="info-detail">
              <span class="detail-label">Hours:</span>
              <p>{{ location.hours }}</p>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- Contact Form Section -->
    <section class="form-section">
      <div class="form-container">
        <div class="form-wrapper">
          <h2 class="form-title">Send us a Message</h2>
          <p class="form-subtitle">
            Have a question or want to get involved? Fill out the form below and we'll get back to
            you shortly.
          </p>

          <!-- Contact Form - Netlify Compatible -->
          <form
            @submit.prevent="handleSubmit"
            name="contact"
            method="POST"
            data-netlify="true"
            netlify-honeypot="bot-field"
            class="contact-form"
          >
            <!-- Hidden inputs for Netlify -->
            <input type="hidden" name="form-name" value="contact" />
            <input type="hidden" name="bot-field" />

            <!-- Name Field -->
            <div class="form-group">
              <label for="name" class="form-label">Full Name *</label>
              <input
                id="name"
                v-model="formData.name"
                type="text"
                name="name"
                class="form-input"
                placeholder="Your full name"
                required
              />
            </div>

            <!-- Email Field -->
            <div class="form-group">
              <label for="email" class="form-label">Email Address *</label>
              <input
                id="email"
                v-model="formData.email"
                type="email"
                name="email"
                class="form-input"
                placeholder="your.email@example.com"
                required
              />
            </div>

            <!-- Phone Field -->
            <div class="form-group">
              <label for="phone" class="form-label">Phone Number</label>
              <input
                id="phone"
                v-model="formData.phone"
                type="tel"
                name="phone"
                class="form-input"
                placeholder="(555) 123-4567"
              />
            </div>

            <!-- Service Interest -->
            <div class="form-group">
              <label for="service" class="form-label">Interest in Service *</label>
              <select
                id="service"
                v-model="formData.service"
                name="service"
                class="form-input"
                required
              >
                <option value="">Select a service</option>
                <option value="Education">Education & Skills Development</option>
                <option value="Healthcare">Healthcare & Wellness</option>
                <option value="Economic Empowerment">Economic Empowerment</option>
                <option value="Environmental">Environmental Conservation</option>
                <option value="Volunteering">Volunteering Opportunities</option>
                <option value="Donation">Donation Information</option>
                <option value="Partnership">Partnership Inquiry</option>
                <option value="Other">Other</option>
              </select>
            </div>

            <!-- Subject Field -->
            <div class="form-group">
              <label for="subject" class="form-label">Subject *</label>
              <input
                id="subject"
                v-model="formData.subject"
                type="text"
                name="subject"
                class="form-input"
                placeholder="How can we help?"
                required
              />
            </div>

            <!-- Message Field -->
            <div class="form-group">
              <label for="message" class="form-label">Message *</label>
              <textarea
                id="message"
                v-model="formData.message"
                name="message"
                class="form-textarea"
                placeholder="Tell us more about your inquiry..."
                rows="6"
                required
              ></textarea>
            </div>

            <!-- Submit Button -->
            <button type="submit" class="submit-button" :disabled="submitStatus === 'submitting'">
              <span v-if="submitStatus === 'submitting'" class="button-text">Sending...</span>
              <span v-else class="button-text">Send Message</span>
            </button>

            <!-- Success Message -->
            <div v-if="submitStatus === 'success'" class="success-message">
              ✓ Thank you! Your message has been sent successfully. We'll get back to you soon.
            </div>

            <!-- Error Message -->
            <div v-if="submitStatus === 'error'" class="error-message">
              ✗ {{ errorMessage }}
            </div>
          </form>
        </div>

        <!-- Additional Contact Methods -->
        <div class="additional-info">
          <h3 class="additional-title">Other Ways to Reach Us</h3>

          <div class="contact-methods">
            <div class="method">
              <div class="method-icon">📞</div>
              <div class="method-content">
                <h4 class="method-title">Call Us</h4>
                <p class="method-text">
                  Available Monday to Friday, 9 AM - 5 PM
                  <br />
                  <a href="tel:+15551234567" class="method-link">+1 (555) 123-4567</a>
                </p>
              </div>
            </div>

            <div class="method">
              <div class="method-icon">📧</div>
              <div class="method-content">
                <h4 class="method-title">Email Us</h4>
                <p class="method-text">
                  We respond to all emails within 24 hours
                  <br />
                  <a href="mailto:info@whlif.org" class="method-link">info@whlif.org</a>
                </p>
              </div>
            </div>

            <div class="method">
              <div class="method-icon">🕐</div>
              <div class="method-content">
                <h4 class="method-title">Quick Response</h4>
                <p class="method-text">
                  For urgent matters, contact our helpline
                  <br />
                  <a href="tel:+15559998888" class="method-link">+1 (555) 999-8888</a>
                </p>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- FAQ Section -->
    <section class="faq-section">
      <div class="faq-container">
        <h2 class="section-title">Frequently Asked Questions</h2>

        <div class="faq-accordion">
          <div
            v-for="item in faqItems"
            :key="item.id"
            class="faq-item"
            :class="{ active: expandedFaqId === item.id }"
          >
            <button
              class="faq-header"
              @click="toggleFaq(item.id)"
              :aria-expanded="expandedFaqId === item.id"
            >
              <h3 class="faq-question">{{ item.question }}</h3>
              <span class="faq-icon">{{ expandedFaqId === item.id ? '−' : '+' }}</span>
            </button>
            <div v-if="expandedFaqId === item.id" class="faq-content">
              <p class="faq-answer">{{ item.answer }}</p>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- Map Section (Optional) -->
    <section class="map-section">
      <div class="map-container">
        <h2 class="section-title">Visit Us</h2>
        <div class="map-placeholder">
          <div class="map-icon">🗺️</div>
          <p>Map integration available when hosted</p>
        </div>
      </div>
    </section>
  </div>
</template>

<style scoped>
.contact {
  width: 100%;
}

/* Page Header */
.page-header {
  background: linear-gradient(135deg, #263a7c 0%, #0f0148 100%);
  color: white;
  padding: 4rem 2rem;
  text-align: center;
}

.header-content {
  max-width: 800px;
  margin: 0 auto;
}

.header-title {
  font-size: 3rem;
  font-weight: 700;
  margin-bottom: 1rem;
}

.header-subtitle {
  font-size: 1.25rem;
  opacity: 0.95;
}

/* Section Title */
.section-title {
  font-size: 2.5rem;
  font-weight: 700;
  margin-bottom: 2rem;
  color: #1e293b;
  text-align: center;
}

/* Info Section */
.info-section {
  padding: 4rem 2rem;
  background-color: #f8f9fa;
}

.info-container {
  max-width: 1200px;
  margin: 0 auto;
}

.info-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
  gap: 2rem;
}

.info-card {
  background-color: white;
  padding: 2.5rem 2rem;
  border-radius: 8px;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.1);
  transition: all 0.3s ease;
}

.info-card:hover {
  transform: translateY(-8px);
  box-shadow: 0 12px 24px rgba(0, 0, 0, 0.15);
}

.info-icon {
  font-size: 2.5rem;
  margin-bottom: 1rem;
}

.info-title {
  font-size: 1.3rem;
  font-weight: 600;
  color: #1e293b;
  margin-bottom: 1.5rem;
}

.info-detail {
  margin-bottom: 1rem;
}

.detail-label {
  font-weight: 600;
  color: #42b983;
  display: block;
  font-size: 0.9rem;
  margin-bottom: 0.25rem;
}

.info-detail p {
  margin: 0;
  color: #555;
  font-size: 0.95rem;
  line-height: 1.6;
}

.info-link {
  color: #42b983;
  text-decoration: none;
  font-weight: 500;
  transition: all 0.3s ease;
}

.info-link:hover {
  color: #359268;
  text-decoration: underline;
}

/* Form Section */
.form-section {
  padding: 4rem 2rem;
  background-color: white;
}

.form-container {
  max-width: 1000px;
  margin: 0 auto;
  display: grid;
  grid-template-columns: 2fr 1fr;
  gap: 3rem;
}

.form-wrapper {
  flex: 1;
}

.form-title {
  font-size: 2rem;
  font-weight: 700;
  color: #1e293b;
  margin-bottom: 1rem;
}

.form-subtitle {
  font-size: 1rem;
  color: #666;
  margin-bottom: 2rem;
  line-height: 1.6;
}

.contact-form {
  display: flex;
  flex-direction: column;
  gap: 1.5rem;
}

.form-group {
  display: flex;
  flex-direction: column;
}

.form-label {
  font-weight: 600;
  color: #1e293b;
  margin-bottom: 0.5rem;
  font-size: 0.95rem;
}

.form-input,
.form-textarea {
  padding: 0.75rem 1rem;
  border: 1px solid #e2e8f0;
  border-radius: 4px;
  font-size: 1rem;
  font-family: inherit;
  transition: all 0.3s ease;
  background-color: #f8f9fa;
}

.form-input:focus,
.form-textarea:focus {
  outline: none;
  border-color: #42b983;
  background-color: white;
  box-shadow: 0 0 0 3px rgba(66, 185, 131, 0.1);
}

.form-textarea {
  resize: vertical;
}

.submit-button {
  padding: 1rem 2rem;
  background-color: #42b983;
  color: white;
  border: none;
  border-radius: 4px;
  font-weight: 600;
  font-size: 1rem;
  cursor: pointer;
  transition: all 0.3s ease;
}

.submit-button:hover:not(:disabled) {
  background-color: #359268;
  transform: translateY(-3px);
  box-shadow: 0 10px 20px rgba(66, 185, 131, 0.3);
}

.submit-button:disabled {
  opacity: 0.7;
  cursor: not-allowed;
}

.button-text {
  display: block;
}

.success-message {
  padding: 1rem;
  background-color: #e8f5e9;
  color: #2e7d32;
  border-left: 4px solid #4caf50;
  border-radius: 4px;
  font-weight: 500;
}

.error-message {
  padding: 1rem;
  background-color: #ffebee;
  color: #c62828;
  border-left: 4px solid #f44336;
  border-radius: 4px;
  font-weight: 500;
}

/* Additional Info */
.additional-info {
  background-color: #f8f9fa;
  padding: 2rem;
  border-radius: 8px;
}

.additional-title {
  font-size: 1.3rem;
  font-weight: 600;
  color: #1e293b;
  margin-bottom: 1.5rem;
}

.contact-methods {
  display: flex;
  flex-direction: column;
  gap: 1.5rem;
}

.method {
  display: flex;
  gap: 1rem;
  padding-bottom: 1.5rem;
  border-bottom: 1px solid #e2e8f0;
}

.method:last-child {
  border-bottom: none;
  padding-bottom: 0;
}

.method-icon {
  font-size: 2rem;
  flex-shrink: 0;
}

.method-content {
  flex: 1;
}

.method-title {
  font-weight: 600;
  color: #1e293b;
  margin-bottom: 0.5rem;
  font-size: 0.95rem;
}

.method-text {
  font-size: 0.9rem;
  color: #666;
  margin: 0;
  line-height: 1.6;
}

.method-link {
  color: #42b983;
  text-decoration: none;
  font-weight: 500;
  transition: all 0.3s ease;
}

.method-link:hover {
  color: #359268;
  text-decoration: underline;
}

/* FAQ Section */
.faq-section {
  padding: 4rem 2rem;
  background-color: #f8f9fa;
}

.faq-container {
  max-width: 900px;
  margin: 0 auto;
}

.faq-accordion {
  display: flex;
  flex-direction: column;
  gap: 1rem;
}

.faq-item {
  background-color: white;
  border-radius: 8px;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.1);
  overflow: hidden;
  transition: all 0.3s ease;
}

.faq-item:hover {
  box-shadow: 0 4px 12px rgba(0, 0, 0, 0.15);
}

.faq-item.active {
  box-shadow: 0 8px 20px rgba(0, 0, 0, 0.15);
}

.faq-header {
  width: 100%;
  padding: 1.5rem 2rem;
  background-color: white;
  border: none;
  cursor: pointer;
  display: flex;
  align-items: center;
  justify-content: space-between;
  gap: 1rem;
  transition: all 0.3s ease;
}

.faq-item.active .faq-header {
  background-color: #f8f9fa;
}

.faq-header:hover {
  background-color: #f8f9fa;
}

.faq-question {
  font-size: 1.05rem;
  font-weight: 600;
  color: #1e293b;
  margin: 0;
  text-align: left;
  flex: 1;
}

.faq-icon {
  font-size: 1.5rem;
  color: #42b983;
  font-weight: bold;
  flex-shrink: 0;
  transition: all 0.3s ease;
}

.faq-item.active .faq-icon {
  color: #359268;
}

.faq-content {
  padding: 0 2rem 1.5rem 2rem;
  animation: slideDown 0.3s ease-out;
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

.faq-answer {
  font-size: 0.95rem;
  color: #555;
  line-height: 1.8;
  margin: 0;
}

/* Map Section */
.map-section {
  padding: 4rem 2rem;
  background-color: white;
}

.map-container {
  max-width: 1200px;
  margin: 0 auto;
}

.map-placeholder {
  width: 100%;
  height: 400px;
  background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
  border-radius: 8px;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  color: white;
  gap: 1rem;
  box-shadow: 0 4px 12px rgba(0, 0, 0, 0.1);
}

.map-icon {
  font-size: 4rem;
}

.map-placeholder p {
  font-size: 1.1rem;
  opacity: 0.9;
}

/* Responsive Design */
@media (max-width: 768px) {
  .header-title {
    font-size: 2rem;
  }

  .section-title {
    font-size: 2rem;
  }

  .form-container {
    grid-template-columns: 1fr;
  }

  .info-grid {
    grid-template-columns: 1fr;
  }

  .faq-grid {
    grid-template-columns: 1fr;
  }

  .contact-methods {
    gap: 1rem;
  }

  .method {
    padding-bottom: 1rem;
  }

  .info-section,
  .form-section,
  .faq-section,
  .map-section {
    padding: 2rem 1.5rem;
  }
}

@media (max-width: 480px) {
  .page-header {
    padding: 2rem 1rem;
  }

  .header-title {
    font-size: 1.5rem;
  }

  .header-subtitle {
    font-size: 0.9rem;
  }

  .section-title {
    font-size: 1.5rem;
  }

  .form-title {
    font-size: 1.3rem;
  }

  .faq-grid {
    grid-template-columns: 1fr;
  }

  .map-placeholder {
    height: 300px;
  }
}
</style>
