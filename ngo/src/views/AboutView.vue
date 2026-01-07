<script setup lang="ts">
import { RouterLink } from 'vue-router'
</script>

<template>
  <div class="about">
    <!-- Page Header -->
    <section class="page-header">
      <div class="header-content">
        <h1 class="header-title">About Our Organization</h1>
        <p class="header-subtitle">Empowering Communities, Building a Better Future</p>
      </div>
    </section>

    <!-- Mission, Vision, Values Section -->
    <section class="mission-section">
      <div class="mission-container">
        <div class="mission-card">
          <div class="card-icon">🎯</div>
          <h2 class="card-title">Our Mission</h2>
          <p class="card-text">
            To empower individuals and communities through sustainable development initiatives,
            quality education, healthcare access, and environmental conservation. We work to
            create lasting positive change that addresses root causes of poverty and inequality.
          </p>
        </div>

        <div class="mission-card">
          <div class="card-icon">🌟</div>
          <h2 class="card-title">Our Vision</h2>
          <p class="card-text">
            A world where every individual has access to education, healthcare, and economic
            opportunities, living in sustainable communities with dignity, hope, and purpose.
            A future where humanity and compassion guide our actions.
          </p>
        </div>

        <div class="mission-card">
          <div class="card-icon">💎</div>
          <h2 class="card-title">Our Values</h2>
          <p class="card-text">
            Integrity, Compassion, Transparency, Inclusivity, and Sustainability guide every
            decision we make. We believe in community-led solutions and respect for human dignity.
          </p>
        </div>
      </div>
    </section>

    <!-- Our Story Section -->
    <section class="story-section">
      <div class="story-container">
        <div class="story-content">
          <h2 class="section-title">Our Story</h2>
          <p class="story-text">
            We are Non Governmental Organizations founded in 2010 with a simple belief:
            that every person deserves access to basic needs and opportunities for growth. What
            started as a small grassroots movement has grown into a dynamic organization making
            tangible differences in communities across the region.
          </p>
          <p class="story-text">
            Our journey has been shaped by the communities we serve. We've learned that sustainable
            change comes from listening, partnering, and empowering local leaders. Over the past
            15 years, we've stayed true to our commitment: putting people first and creating
            solutions that last.
          </p>
          <p class="story-text">
            Today, our team comprises passionate professionals, dedicated volunteers, and community
            partners working in unison to address poverty, improve education, enhance healthcare
            access, and protect our environment. Every project we undertake is guided by the voices
            and needs of the communities we serve.
          </p>
        </div>
        <div class="story-image">
          <div class="image-placeholder">🤝</div>
        </div>
      </div>
    </section>

    <!-- Core Focus Areas -->
    <section class="focus-section">
      <div class="focus-container">
        <h2 class="section-title">Our Focus Areas</h2>

        <div class="focus-grid">
          <div class="focus-card">
            <div class="focus-number">01</div>
            <div class="focus-icon">📚</div>
            <h3 class="focus-title">Education & Skills Development</h3>
            <p class="focus-description">
              We provide quality education and vocational training to underserved children and
              youth, empowering them with skills for sustainable livelihoods and personal growth.
            </p>
            <ul class="focus-list">
              <li>Primary and secondary education programs</li>
              <li>Vocational skills training</li>
              <li>Scholarship programs</li>
              <li>Teacher training initiatives</li>
            </ul>
          </div>

          <div class="focus-card">
            <div class="focus-number">02</div>
            <div class="focus-icon">⚕️</div>
            <h3 class="focus-title">Healthcare & Wellness</h3>
            <p class="focus-description">
              We work to improve health outcomes by providing access to preventive care,
              treatment, and health education in underserved communities.
            </p>
            <ul class="focus-list">
              <li>Health camps and screenings</li>
              <li>Maternal and child health programs</li>
              <li>Health awareness campaigns</li>
              <li>Access to essential medicines</li>
            </ul>
          </div>

          <div class="focus-card">
            <div class="focus-number">03</div>
            <div class="focus-icon">👩‍💼</div>
            <h3 class="focus-title">Economic Empowerment</h3>
            <p class="focus-description">
              We enable economic independence through microfinance, entrepreneurship training,
              and livelihood programs for vulnerable populations.
            </p>
            <ul class="focus-list">
              <li>Microfinance and lending programs</li>
              <li>Entrepreneurship training</li>
              <li>Women's economic initiatives</li>
              <li>Market linkage programs</li>
            </ul>
          </div>

          <div class="focus-card">
            <div class="focus-number">04</div>
            <div class="focus-icon">🌱</div>
            <h3 class="focus-title">Environmental Conservation</h3>
            <p class="focus-description">
              We promote sustainable practices and environmental conservation for a healthier
              planet and resilient communities.
            </p>
            <ul class="focus-list">
              <li>Reforestation projects</li>
              <li>Water and sanitation initiatives</li>
              <li>Climate action programs</li>
              <li>Waste management solutions</li>
            </ul>
          </div>
        </div>
      </div>
    </section>

    <!-- Impact Metrics -->
    <section class="impact-section">
      <div class="impact-container">
        <h2 class="section-title">Our Impact</h2>
        <p class="impact-subtitle">Measurable change in the lives we touch</p>

        <div class="impact-grid">
          <div class="impact-stat">
            <div class="impact-number">10,000+</div>
            <div class="impact-label">Lives Directly Impacted</div>
            <div class="impact-desc">Through our various programs and initiatives</div>
          </div>

          <div class="impact-stat">
            <div class="impact-number">50+</div>
            <div class="impact-label">Projects Completed</div>
            <div class="impact-desc">Across education, health, and environment</div>
          </div>

          <div class="impact-stat">
            <div class="impact-number">2,000+</div>
            <div class="impact-label">Children in School</div>
            <div class="impact-desc">With ongoing educational support</div>
          </div>

          <div class="impact-stat">
            <div class="impact-number">5,000+</div>
            <div class="impact-label">Healthcare Beneficiaries</div>
            <div class="impact-desc">Accessed medical services annually</div>
          </div>

          <div class="impact-stat">
            <div class="impact-number">500+</div>
            <div class="impact-label">Entrepreneurs Trained</div>
            <div class="impact-desc">With active livelihood support</div>
          </div>

          <div class="impact-stat">
            <div class="impact-number">50,000+</div>
            <div class="impact-label">Trees Planted</div>
            <div class="impact-desc">For environmental restoration</div>
          </div>
        </div>
      </div>
    </section>

    <!-- Organizational Structure -->
    <section class="structure-section">
      <div class="structure-container">
        <h2 class="section-title">Leadership Team</h2>

        <div class="leadership-grid">
          <div class="leader-card">
            <div class="leader-avatar">👩‍💼</div>
            <h3 class="leader-name">Sarah Johnson</h3>
            <p class="leader-role">Executive Director</p>
            <p class="leader-bio">
              With 20 years of experience in international development, Sarah leads our
              organizational vision and strategic direction.
            </p>
          </div>

          <div class="leader-card">
            <div class="leader-avatar">👨‍💼</div>
            <h3 class="leader-name">Michael Chen</h3>
            <p class="leader-role">Programs Director</p>
            <p class="leader-bio">
              Michael oversees all program implementation and ensures quality delivery across
              all our initiatives.
            </p>
          </div>

          <div class="leader-card">
            <div class="leader-avatar">👩‍💼</div>
            <h3 class="leader-name">Priya Sharma</h3>
            <p class="leader-role">Community Relations Manager</p>
            <p class="leader-bio">
              Priya facilitates community partnerships and ensures our work remains grounded
              in local needs.
            </p>
          </div>

          <div class="leader-card">
            <div class="leader-avatar">👨‍💼</div>
            <h3 class="leader-name">David Williams</h3>
            <p class="leader-role">Finance & Operations Manager</p>
            <p class="leader-bio">
              David ensures transparent financial management and operational excellence in
              everything we do.
            </p>
          </div>
        </div>
      </div>
    </section>

    <!-- Partnerships Section -->
    <section class="partnerships-section">
      <div class="partnerships-container">
        <h2 class="section-title">Our Partners</h2>
        <p class="partnerships-subtitle">
          We collaborate with government agencies, NGOs, corporations, and community organizations
          to maximize our impact.
        </p>

        <div class="partners-grid">
          <div class="partner-item">
            <div class="partner-logo">🏢</div>
            <p>Government Agencies</p>
          </div>
          <div class="partner-item">
            <div class="partner-logo">🏫</div>
            <p>Educational Institutions</p>
          </div>
          <div class="partner-item">
            <div class="partner-logo">🏥</div>
            <p>Healthcare Organizations</p>
          </div>
          <div class="partner-item">
            <div class="partner-logo">🌍</div>
            <p>International NGOs</p>
          </div>
          <div class="partner-item">
            <div class="partner-logo">💼</div>
            <p>Corporate Partners</p>
          </div>
          <div class="partner-item">
            <div class="partner-logo">👥</div>
            <p>Community Groups</p>
          </div>
        </div>
      </div>
    </section>

    <!-- Call to Action -->
    <section class="cta-section">
      <div class="cta-container">
        <h2 class="cta-title">Join Our Movement</h2>
        <p class="cta-text">
          Be part of the change. Whether you volunteer, donate, or partner with us, your
          contribution matters.
        </p>
        <div class="cta-buttons">
          <RouterLink to="/contact" class="cta-button primary">Get Involved</RouterLink>
          <RouterLink to="/contact" class="cta-button secondary">Donate Now</RouterLink>
        </div>
      </div>
    </section>
  </div>
</template>

<style scoped>
.about {
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
  margin-bottom: 0.5rem;
  color: #1e293b;
  text-align: center;
}

/* Mission Section */
.mission-section {
  padding: 4rem 2rem;
  background-color: #f8f9fa;
}

.mission-container {
  max-width: 1200px;
  margin: 0 auto;
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  gap: 2rem;
}

.mission-card {
  background-color: white;
  padding: 2.5rem 2rem;
  border-radius: 8px;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.1);
  text-align: center;
  transition: all 0.3s ease;
}

.mission-card:hover {
  transform: translateY(-8px);
  box-shadow: 0 12px 24px rgba(0, 0, 0, 0.15);
}

.card-icon {
  font-size: 3rem;
  margin-bottom: 1rem;
}

.card-title {
  font-size: 1.5rem;
  font-weight: 600;
  margin-bottom: 1rem;
  color: #1e293b;
}

.card-text {
  font-size: 0.95rem;
  color: #666;
  line-height: 1.8;
}

/* Story Section */
.story-section {
  padding: 4rem 2rem;
  background-color: white;
}

.story-container {
  max-width: 1200px;
  margin: 0 auto;
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 3rem;
  align-items: center;
  margin-top: 2rem;
}

.story-content {
  flex: 1;
}

.story-text {
  font-size: 1.05rem;
  color: #555;
  line-height: 1.8;
  margin-bottom: 1.5rem;
}

.story-image {
  flex: 1;
  display: flex;
  align-items: center;
  justify-content: center;
}

.image-placeholder {
  width: 100%;
  height: 400px;
  background: linear-gradient(135deg, #f093fb 0%, #f5576c 100%);
  border-radius: 12px;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 6rem;
  box-shadow: 0 10px 30px rgba(0, 0, 0, 0.1);
}

/* Focus Section */
.focus-section {
  padding: 4rem 2rem;
  background-color: #f8f9fa;
}

.focus-container {
  max-width: 1200px;
  margin: 0 auto;
}

.focus-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
  gap: 2rem;
  margin-top: 2rem;
}

.focus-card {
  background-color: white;
  padding: 2rem;
  border-radius: 8px;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.1);
  transition: all 0.3s ease;
  position: relative;
  overflow: hidden;
}

.focus-card::before {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  height: 4px;
  background: linear-gradient(90deg, #667eea 0%, #42b983 100%);
}

.focus-card:hover {
  transform: translateY(-8px);
  box-shadow: 0 12px 24px rgba(0, 0, 0, 0.15);
}

.focus-number {
  font-size: 3rem;
  font-weight: 700;
  color: #e2e8f0;
  margin-bottom: 0.5rem;
}

.focus-icon {
  font-size: 2.5rem;
  margin-bottom: 1rem;
}

.focus-title {
  font-size: 1.3rem;
  font-weight: 600;
  margin-bottom: 1rem;
  color: #1e293b;
}

.focus-description {
  font-size: 0.95rem;
  color: #666;
  margin-bottom: 1.5rem;
  line-height: 1.6;
}

.focus-list {
  list-style: none;
  padding: 0;
  display: flex;
  flex-direction: column;
  gap: 0.75rem;
}

.focus-list li {
  font-size: 0.9rem;
  color: #555;
  padding-left: 1.5rem;
  position: relative;
}

.focus-list li::before {
  content: '✓';
  position: absolute;
  left: 0;
  color: #42b983;
  font-weight: bold;
}

/* Impact Section */
.impact-section {
  padding: 4rem 2rem;
  background-color: white;
}

.impact-container {
  max-width: 1200px;
  margin: 0 auto;
}

.impact-subtitle {
  font-size: 1.1rem;
  color: #666;
  text-align: center;
  margin-bottom: 3rem;
}

.impact-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
  gap: 2rem;
}

.impact-stat {
  background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
  color: white;
  padding: 2rem;
  border-radius: 8px;
  text-align: center;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.1);
  transition: all 0.3s ease;
}

.impact-stat:hover {
  transform: translateY(-5px);
  box-shadow: 0 8px 16px rgba(0, 0, 0, 0.2);
}

.impact-number {
  font-size: 2.5rem;
  font-weight: 700;
  margin-bottom: 0.5rem;
}

.impact-label {
  font-size: 1.1rem;
  font-weight: 600;
  margin-bottom: 0.5rem;
}

.impact-desc {
  font-size: 0.9rem;
  opacity: 0.9;
}

/* Leadership Section */
.structure-section {
  padding: 4rem 2rem;
  background-color: #f8f9fa;
}

.structure-container {
  max-width: 1200px;
  margin: 0 auto;
}

.leadership-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
  gap: 2rem;
  margin-top: 2rem;
}

.leader-card {
  background-color: white;
  padding: 2rem;
  border-radius: 8px;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.1);
  text-align: center;
  transition: all 0.3s ease;
}

.leader-card:hover {
  transform: translateY(-8px);
  box-shadow: 0 12px 24px rgba(0, 0, 0, 0.15);
}

.leader-avatar {
  font-size: 3.5rem;
  margin-bottom: 1rem;
}

.leader-name {
  font-size: 1.2rem;
  font-weight: 600;
  margin-bottom: 0.5rem;
  color: #1e293b;
}

.leader-role {
  font-size: 1rem;
  color: #42b983;
  font-weight: 600;
  margin-bottom: 1rem;
}

.leader-bio {
  font-size: 0.9rem;
  color: #666;
  line-height: 1.6;
}

/* Partnerships Section */
.partnerships-section {
  padding: 4rem 2rem;
  background-color: white;
}

.partnerships-container {
  max-width: 1200px;
  margin: 0 auto;
}

.partnerships-subtitle {
  font-size: 1.1rem;
  color: #666;
  text-align: center;
  margin-bottom: 3rem;
}

.partners-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
  gap: 2rem;
}

.partner-item {
  background-color: #f8f9fa;
  padding: 2rem;
  border-radius: 8px;
  text-align: center;
  transition: all 0.3s ease;
  border: 2px solid transparent;
}

.partner-item:hover {
  border-color: #42b983;
  background-color: #e8f5e9;
}

.partner-logo {
  font-size: 3rem;
  margin-bottom: 1rem;
}

.partner-item p {
  font-size: 1rem;
  font-weight: 500;
  color: #1e293b;
}

/* CTA Section */
.cta-section {
  padding: 4rem 2rem;
  background: linear-gradient(135deg, #4facfe 0%, #00f2fe 100%);
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

.cta-button {
  display: inline-block;
  padding: 1rem 2rem;
  border-radius: 4px;
  font-weight: 600;
  text-decoration: none;
  transition: all 0.3s ease;
  border: 2px solid white;
}

.cta-button.primary {
  background-color: white;
  color: #4facfe;
}

.cta-button.primary:hover {
  transform: translateY(-3px);
  box-shadow: 0 10px 20px rgba(0, 0, 0, 0.2);
}

.cta-button.secondary {
  background-color: transparent;
  color: white;
}

.cta-button.secondary:hover {
  background-color: white;
  color: #4facfe;
}

/* Responsive Design */
@media (max-width: 768px) {
  .header-title {
    font-size: 2rem;
  }

  .header-subtitle {
    font-size: 1rem;
  }

  .section-title {
    font-size: 2rem;
  }

  .story-container {
    grid-template-columns: 1fr;
  }

  .image-placeholder {
    height: 300px;
    font-size: 4rem;
  }

  .leadership-grid {
    grid-template-columns: 1fr;
  }

  .cta-buttons {
    flex-direction: column;
  }

  .cta-button {
    width: 100%;
    text-align: center;
  }

  .mission-section,
  .story-section,
  .focus-section,
  .impact-section,
  .structure-section,
  .partnerships-section,
  .cta-section {
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

  .story-text {
    font-size: 0.9rem;
  }

  .cta-title {
    font-size: 1.75rem;
  }

  .impact-number {
    font-size: 2rem;
  }

  .mission-card,
  .focus-card,
  .leader-card {
    padding: 1.5rem;
  }
}
</style>
