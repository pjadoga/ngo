<script setup lang="ts">
import { ref, onMounted, onUnmounted } from 'vue'
import { RouterLink } from 'vue-router'

const currentSlide = ref(0)
const slides = [
  {
    title: 'Making a Difference Together',
    subtitle: 'Empowering communities, changing lives',
    image: 'linear-gradient(135deg, #667eea 0%, #764ba2 100%)'
  },
  {
    title: 'Building a Better Future',
    subtitle: 'Sustainable solutions for lasting change',
    image: 'linear-gradient(135deg, #f093fb 0%, #f5576c 100%)'
  },
  {
    title: 'Creating Positive Impact',
    subtitle: 'Your support makes a real difference',
    image: 'linear-gradient(135deg, #4facfe 0%, #00f2fe 100%)'
  }
]

const stats = [
  { number: '10K+', label: 'Lives Impacted', icon: '👥' },
  { number: '50+', label: 'Projects Completed', icon: '🎯' },
  { number: '15+', label: 'Years of Service', icon: '⏰' },
  { number: '25+', label: 'Volunteers', icon: '🤝' }
]

const services = [
  { title: 'Community Development', description: 'Building stronger communities through education and empowerment', icon: '🏘️' },
  { title: 'Education Programs', description: 'Quality education initiatives for underprivileged children', icon: '📚' },
  { title: 'Healthcare Initiatives', description: 'Providing access to basic healthcare and wellness programs', icon: '⚕️' },
  { title: 'Environmental Projects', description: 'Sustainable solutions for environmental conservation', icon: '🌱' }
]

const projects = [
  {
    id: 1,
    title: 'Rural Education Initiative',
    description: 'Providing quality education to 500+ children in rural areas',
    category: 'Education',
    image: 'linear-gradient(135deg, #667eea 0%, #764ba2 100%)'
  },
  {
    id: 2,
    title: 'Healthcare Camp 2024',
    description: 'Free medical services reached 2000+ community members',
    category: 'Healthcare',
    image: 'linear-gradient(135deg, #f093fb 0%, #f5576c 100%)'
  },
  {
    id: 3,
    title: 'Green Earth Initiative',
    description: 'Planted 10,000 trees in urban and rural areas',
    category: 'Environment',
    image: 'linear-gradient(135deg, #4facfe 0%, #00f2fe 100%)'
  },
  {
    id: 4,
    title: 'Women Empowerment',
    description: 'Skills training for 300+ women entrepreneurs',
    category: 'Development',
    image: 'linear-gradient(135deg, #43e97b 0%, #38f9d7 100%)'
  }
]

const team = [
  { name: 'Justin Adoga', role: 'Executive Director', icon: '👨‍💼' },
  { name: 'Amina Yusuf', role: 'Project Manager', icon: '👩‍💼' },
  { name: 'Michael Chen', role: 'Programs Manager', icon: '👨‍💼' },
  { name: 'Priya Sharma', role: 'Community Coordinator', icon: '👩‍💼' },
]

let slideInterval: ReturnType<typeof setInterval> | null = null

onMounted(() => {
  slideInterval = setInterval(() => {
    currentSlide.value = (currentSlide.value + 1) % slides.length
  }, 5000)
})

onUnmounted(() => {
  if (slideInterval) clearInterval(slideInterval)
})

const nextSlide = () => {
  currentSlide.value = (currentSlide.value + 1) % slides.length
}

const prevSlide = () => {
  currentSlide.value = (currentSlide.value - 1 + slides.length) % slides.length
}
</script>

<template>
  <!-- Hero Section with Sliding Background -->
  <section class="hero-section">
    <div
      class="slide"
      :style="{ background: slides[currentSlide]?.image }"
      :class="{ active: true }"
    >
      <div class="slide-overlay"></div>
      <div class="hero-content">
        <h1 class="hero-title">{{ slides[currentSlide]?.title }}</h1>
        <p class="hero-subtitle">{{ slides[currentSlide]?.subtitle }}</p>
        <RouterLink to="/contact" class="cta-button">Get Involved Today</RouterLink>
      </div>
    </div>

    <!-- Slide Controls -->
    <button class="slide-control prev" @click="prevSlide" aria-label="Previous slide">❮</button>
    <button class="slide-control next" @click="nextSlide" aria-label="Next slide">❯</button>

    <!-- Slide Indicators -->
    <div class="slide-indicators">
      <button
        v-for="(slide, index) in slides"
        :key="index"
        class="indicator"
        :class="{ active: index === currentSlide }"
        @click="currentSlide = index"
        :aria-label="`Go to slide ${index + 1}`"
      ></button>
    </div>
  </section>

  <!-- Stats Section -->
  <section class="stats-section">
    <div class="stats-container">
      <div v-for="stat in stats" :key="stat.label" class="stat-card">
        <div class="stat-icon">{{ stat.icon }}</div>
        <div class="stat-number">{{ stat.number }}</div>
        <div class="stat-label">{{ stat.label }}</div>
      </div>
    </div>
  </section>

  <!-- About Section -->
  <section class="about-section">
    <div class="about-container">
      <div class="about-content">
        <h2 class="section-title">About Us</h2>
        <h3 class="section-subtitle">Our NGO Foundation</h3>
        <p class="about-text">
          We are a non-profit organization dedicated to creating sustainable positive change in
          underserved communities. For over 15 years, our team has been committed to addressing
          critical social issues through innovative programs and community-driven solutions.
        </p>
        <p class="about-text">
          Our mission is to empower individuals and communities by providing access to quality
          education, healthcare, and economic opportunities while promoting environmental
          sustainability and social equity.
        </p>
        <div class="about-features">
          <div class="feature">
            <span class="feature-icon">✓</span>
            <span>Community-Centered Approach</span>
          </div>
          <div class="feature">
            <span class="feature-icon">✓</span>
            <span>Sustainable Solutions</span>
          </div>
          <div class="feature">
            <span class="feature-icon">✓</span>
            <span>Transparent Operations</span>
          </div>
          <div class="feature">
            <span class="feature-icon">✓</span>
            <span>Long-term Impact</span>
          </div>
        </div>
      </div>
      <div class="about-image">
        <div class="image-placeholder">🌍</div>
      </div>
    </div>
  </section>

  <!-- Services Section -->
  <section class="services-section">
    <div class="services-container">
      <h2 class="section-title">Our Services</h2>
      <p class="section-description">We provide comprehensive programs across multiple sectors</p>
      <div class="services-grid">
        <div v-for="service in services" :key="service.title" class="service-card">
          <div class="service-icon">{{ service.icon }}</div>
          <h3 class="service-title">{{ service.title }}</h3>
          <p class="service-description">{{ service.description }}</p>
        </div>
      </div>
    </div>
  </section>

  <!-- Projects Section -->
  <section class="projects-section">
    <div class="projects-container">
      <h2 class="section-title">Recent Projects</h2>
      <p class="section-description">Showcasing our recent initiatives and achievements</p>
      <div class="projects-grid">
        <div v-for="project in projects" :key="project.id" class="project-card">
          <div class="project-image" :style="{ background: project.image }"></div>
          <div class="project-content">
            <span class="project-category">{{ project.category }}</span>
            <h3 class="project-title">{{ project.title }}</h3>
            <p class="project-description">{{ project.description }}</p>
            <RouterLink to="/contact" class="read-more">Learn More →</RouterLink>
          </div>
        </div>
      </div>
    </div>
  </section>

  <!-- Team Section -->
  <section class="team-section">
    <div class="team-container">
      <h2 class="section-title">Our Team</h2>
      <p class="section-description">Dedicated professionals working towards positive change</p>
      <div class="team-grid">
        <div v-for="member in team" :key="member.name" class="team-card">
          <div class="team-avatar">{{ member.icon }}</div>
          <h3 class="team-name">{{ member.name }}</h3>
          <p class="team-role">{{ member.role }}</p>
        </div>
      </div>
    </div>
  </section>

  <!-- Call to Action Section -->
  <section class="cta-section">
    <div class="cta-container">
      <h2 class="cta-title">Make a Difference Today</h2>
      <p class="cta-text">
        Your support can change lives. Join us in our mission to create a better world for everyone.
      </p>
      <div class="cta-buttons">
        <RouterLink to="/contact" class="cta-button primary">Donate Now</RouterLink>
        <RouterLink to="/about" class="cta-button secondary">Learn More</RouterLink>
      </div>
    </div>
  </section>

  <!-- Newsletter Section -->
  <section class="newsletter-section">
    <div class="newsletter-container">
      <h2 class="newsletter-title">Stay Updated</h2>
      <p class="newsletter-description">Subscribe to our newsletter for updates on our initiatives</p>
      <form class="newsletter-form" @submit.prevent>
        <input type="email" placeholder="Enter your email" class="newsletter-input" required />
        <button type="submit" class="newsletter-submit">Subscribe</button>
      </form>
    </div>
  </section>
</template>

<style scoped>
/* Hero Section */
.hero-section {
  position: relative;
  width: 100%;
  height: 600px;
  overflow: hidden;
}

.slide {
  position: absolute;
  width: 100%;
  height: 100%;
  display: flex;
  align-items: center;
  justify-content: center;
  opacity: 0;
  transition: opacity 0.8s ease-in-out;
}

.slide.active {
  opacity: 1;
}

.slide-overlay {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-color: rgba(0, 0, 0, 0.4);
}

.hero-content {
  position: relative;
  z-index: 10;
  text-align: center;
  color: white;
  animation: slideUp 0.8s ease-out;
}

@keyframes slideUp {
  from {
    opacity: 0;
    transform: translateY(30px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

.hero-title {
  font-size: 3.5rem;
  font-weight: 700;
  margin-bottom: 1rem;
  text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.5);
}

.hero-subtitle {
  font-size: 1.5rem;
  margin-bottom: 2rem;
  text-shadow: 1px 1px 2px rgba(0, 0, 0, 0.5);
}

.cta-button {
  display: inline-block;
  padding: 1rem 2rem;
  background-color: #42b983;
  color: white;
  text-decoration: none;
  border-radius: 4px;
  font-weight: 600;
  transition: all 0.3s ease;
  border: 2px solid #42b983;
}

.cta-button:hover {
  background-color: transparent;
  color: white;
  transform: translateY(-3px);
  box-shadow: 0 10px 20px rgba(0, 0, 0, 0.2);
}

/* Slide Controls */
.slide-control {
  position: absolute;
  top: 50%;
  transform: translateY(-50%);
  background-color: rgba(255, 255, 255, 0.3);
  color: white;
  border: none;
  padding: 1rem 1.25rem;
  font-size: 1.5rem;
  cursor: pointer;
  transition: all 0.3s ease;
  z-index: 20;
}

.slide-control:hover {
  background-color: rgba(255, 255, 255, 0.5);
}

.slide-control.prev {
  left: 2rem;
}

.slide-control.next {
  right: 2rem;
}

/* Slide Indicators */
.slide-indicators {
  position: absolute;
  bottom: 2rem;
  left: 50%;
  transform: translateX(-50%);
  display: flex;
  gap: 0.75rem;
  z-index: 20;
}

.indicator {
  width: 12px;
  height: 12px;
  border-radius: 50%;
  background-color: rgba(255, 255, 255, 0.5);
  border: none;
  cursor: pointer;
  transition: all 0.3s ease;
}

.indicator.active {
  background-color: white;
  width: 32px;
  border-radius: 6px;
}

/* Stats Section */
.stats-section {
  padding: 4rem 2rem;
  background-color: #f8f9fa;
}

.stats-container {
  max-width: 1200px;
  margin: 0 auto;
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
  gap: 2rem;
}

.stat-card {
  text-align: center;
  padding: 2rem;
  background-color: white;
  border-radius: 8px;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.1);
  transition: transform 0.3s ease;
}

.stat-card:hover {
  transform: translateY(-5px);
}

.stat-icon {
  font-size: 2.5rem;
  margin-bottom: 1rem;
}

.stat-number {
  font-size: 2.5rem;
  font-weight: 700;
  color: #42b983;
  margin-bottom: 0.5rem;
}

.stat-label {
  font-size: 1rem;
  color: #666;
}

/* Section Title Styles */
.section-title {
  font-size: 2.5rem;
  font-weight: 700;
  margin-bottom: 0.5rem;
  color: #1e293b;
}

.section-subtitle {
  font-size: 1.25rem;
  color: #42b983;
  margin-bottom: 1rem;
  font-weight: 600;
}

.section-description {
  font-size: 1.1rem;
  color: #666;
  margin-bottom: 3rem;
  max-width: 600px;
}

/* About Section */
.about-section {
  padding: 4rem 2rem;
  background-color: white;
}

.about-container {
  max-width: 1200px;
  margin: 0 auto;
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 3rem;
  align-items: center;
}

.about-content {
  flex: 1;
}

.about-text {
  font-size: 1.05rem;
  line-height: 1.8;
  color: #171b2e;
  margin-bottom: 1.5rem;
}

.about-features {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 1rem;
  margin-top: 2rem;
  color: #0e0327;
}

.feature {
  display: flex;
  align-items: center;
  gap: 0.75rem;
  padding: 0.75rem;
}

.feature-icon {
  font-size: 1.25rem;
  color: #42b983;
  font-weight: bold;
}

.about-image {
  flex: 1;
  display: flex;
  align-items: center;
  justify-content: center;
}

.image-placeholder {
  width: 100%;
  height: 400px;
  background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
  border-radius: 12px;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 6rem;
  box-shadow: 0 10px 30px rgba(0, 0, 0, 0.1);
}

/* Services Section */
.services-section {
  padding: 4rem 2rem;
  background-color: #f8f9fa;
}

.services-container {
  max-width: 1200px;
  margin: 0 auto;
}

.services-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
  gap: 2rem;
}

.service-card {
  background-color: white;
  padding: 2rem;
  border-radius: 8px;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.1);
  text-align: center;
  transition: all 0.3s ease;
}

.service-card:hover {
  transform: translateY(-8px);
  box-shadow: 0 8px 20px rgba(0, 0, 0, 0.15);
  border-top: 4px solid #42b983;
}

.service-icon {
  font-size: 3rem;
  margin-bottom: 1rem;
}

.service-title {
  font-size: 1.25rem;
  font-weight: 600;
  margin-bottom: 1rem;
  color: #1e293b;
}

.service-description {
  font-size: 0.95rem;
  color: #666;
  line-height: 1.6;
}

/* Projects Section */
.projects-section {
  padding: 4rem 2rem;
  background-color: white;
}

.projects-container {
  max-width: 1200px;
  margin: 0 auto;
}

.projects-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
  gap: 2rem;
}

.project-card {
  background-color: white;
  border-radius: 8px;
  overflow: hidden;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.1);
  transition: all 0.3s ease;
}

.project-card:hover {
  transform: translateY(-8px);
  box-shadow: 0 12px 24px rgba(0, 0, 0, 0.15);
}

.project-image {
  width: 100%;
  height: 200px;
  transition: transform 0.3s ease;
}

.project-card:hover .project-image {
  transform: scale(1.05);
}

.project-content {
  padding: 1.5rem;
}

.project-category {
  display: inline-block;
  padding: 0.4rem 0.8rem;
  background-color: #e8f5e9;
  color: #42b983;
  border-radius: 4px;
  font-size: 0.8rem;
  font-weight: 600;
  margin-bottom: 0.75rem;
}

.project-title {
  font-size: 1.2rem;
  font-weight: 600;
  margin-bottom: 0.75rem;
  color: #1e293b;
}

.project-description {
  font-size: 0.95rem;
  color: #666;
  margin-bottom: 1rem;
  line-height: 1.6;
}

.read-more {
  color: #42b983;
  text-decoration: none;
  font-weight: 600;
  transition: all 0.3s ease;
}

.read-more:hover {
  gap: 0.5rem;
  color: #359268;
}

/* Team Section */
.team-section {
  padding: 4rem 2rem;
  background-color: #f8f9fa;
}

.team-container {
  max-width: 1200px;
  margin: 0 auto;
}

.team-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
  gap: 2rem;
}

.team-card {
  background-color: white;
  padding: 2rem;
  border-radius: 8px;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.1);
  text-align: center;
  transition: all 0.3s ease;
}

.team-card:hover {
  transform: translateY(-8px);
  box-shadow: 0 8px 20px rgba(0, 0, 0, 0.15);
}

.team-avatar {
  font-size: 4rem;
  margin-bottom: 1rem;
}

.team-name {
  font-size: 1.1rem;
  font-weight: 600;
  margin-bottom: 0.5rem;
  color: #1e293b;
}

.team-role {
  font-size: 0.95rem;
  color: #42b983;
  font-weight: 500;
}

/* CTA Section */
.cta-section {
  padding: 4rem 2rem;
  background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
  color: white;
  text-align: center;
}

.cta-container {
  max-width: 800px;
  margin: 0 auto;
}

.cta-title {
  font-size: 2.5rem;
  font-weight: 700;
  margin-bottom: 1rem;
}

.cta-text {
  font-size: 1.1rem;
  margin-bottom: 2rem;
  opacity: 0.95;
}

.cta-buttons {
  display: flex;
  gap: 1rem;
  justify-content: center;
  flex-wrap: wrap;
}

.cta-button.primary {
  background-color: #42b983;
  border-color: #42b983;
}

.cta-button.secondary {
  background-color: transparent;
  border-color: white;
  color: white;
}

.cta-button.secondary:hover {
  background-color: white;
  color: #667eea;
}

/* Newsletter Section */
.newsletter-section {
  padding: 3rem 2rem;
  background-color: white;
  border-top: 1px solid #e2e8f0;
}

.newsletter-container {
  max-width: 600px;
  margin: 0 auto;
  text-align: center;
}

.newsletter-title {
  font-size: 1.8rem;
  font-weight: 700;
  margin-bottom: 0.5rem;
  color: #1e293b;
}

.newsletter-description {
  font-size: 1rem;
  color: #666;
  margin-bottom: 1.5rem;
}

.newsletter-form {
  display: flex;
  gap: 0.5rem;
}

.newsletter-input {
  flex: 1;
  padding: 0.75rem 1rem;
  border: 1px solid #e2e8f0;
  border-radius: 4px;
  font-size: 1rem;
  transition: all 0.3s ease;
}

.newsletter-input:focus {
  outline: none;
  border-color: #42b983;
  box-shadow: 0 0 0 3px rgba(66, 185, 131, 0.1);
}

.newsletter-submit {
  padding: 0.75rem 1.5rem;
  background-color: #42b983;
  color: white;
  border: none;
  border-radius: 4px;
  font-weight: 600;
  cursor: pointer;
  transition: all 0.3s ease;
}

.newsletter-submit:hover {
  background-color: #359268;
  transform: translateY(-2px);
}

/* Responsive Design */
@media (max-width: 768px) {
  .hero-title {
    font-size: 2rem;
  }

  .hero-subtitle {
    font-size: 1rem;
  }

  .slide-control {
    padding: 0.75rem 1rem;
    font-size: 1.25rem;
  }

  .slide-control.prev {
    left: 0.5rem;
  }

  .slide-control.next {
    right: 0.5rem;
  }

  .hero-section {
    height: 400px;
  }

  .section-title {
    font-size: 2rem;
  }

  .about-container {
    grid-template-columns: 1fr;
  }

  .about-features {
    grid-template-columns: 1fr;
  }

  .image-placeholder {
    height: 300px;
    font-size: 4rem;
  }

  .cta-buttons {
    flex-direction: column;
  }

  .cta-button {
    width: 100%;
    text-align: center;
  }

  .newsletter-form {
    flex-direction: column;
  }
}

@media (max-width: 480px) {
  .hero-title {
    font-size: 1.5rem;
  }

  .hero-subtitle {
    font-size: 0.9rem;
  }

  .hero-section {
    height: 300px;
  }

  .slide-control {
    padding: 0.5rem 0.75rem;
    font-size: 1rem;
  }

  .stats-container {
    grid-template-columns: 1fr 1fr;
  }

  .stat-number {
    font-size: 2rem;
  }

  .section-title {
    font-size: 1.5rem;
  }

  .about-text {
    font-size: 0.95rem;
  }

  .cta-title {
    font-size: 1.75rem;
  }
}
</style>
