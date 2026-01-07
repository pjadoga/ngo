<script setup lang="ts">
import { RouterLink } from 'vue-router'
</script>

<template>
  <div class="services">
    <!-- Page Header -->
    <section class="page-header">
      <div class="header-content">
        <h1 class="header-title">Our Services</h1>
        <p class="header-subtitle">Comprehensive Programs Transforming Lives</p>
      </div>
    </section>

    <!-- Main Services Grid -->
    <section class="main-services-section">
      <div class="services-container">
        <h2 class="section-title">What We Offer</h2>

        <!-- Education Services -->
        <div class="service-block">
          <div class="service-header">
            <div class="service-icon-large">📚</div>
            <h3 class="service-heading">Education & Skills Development</h3>
          </div>
          <p class="service-intro">
            We believe education is the foundation for breaking cycles of poverty and creating
            opportunities for sustainable development.
          </p>

          <div class="service-details-grid">
            <div class="detail-item">
              <div class="detail-icon">🎓</div>
              <h4 class="detail-title">Primary Education Programs</h4>
              <p class="detail-text">
                Quality education for children aged 6-11 in rural and underserved areas. Focus on
                literacy, numeracy, and foundational skills development.
              </p>
              <ul class="feature-list">
                <li>Free enrollment and materials</li>
                <li>Trained & dedicated teachers</li>
                <li>Safe learning environment</li>
                <li>Regular progress monitoring</li>
              </ul>
            </div>

            <div class="detail-item">
              <div class="detail-icon">👨‍🎓</div>
              <h4 class="detail-title">Secondary Education Support</h4>
              <p class="detail-text">
                Continuation programs for students aged 12-18, with emphasis on STEM subjects and
                critical thinking skills.
              </p>
              <ul class="feature-list">
                <li>Scholarship programs</li>
                <li>Career guidance</li>
                <li>Exam preparation</li>
                <li>Mentoring support</li>
              </ul>
            </div>

            <div class="detail-item">
              <div class="detail-icon">🔧</div>
              <h4 class="detail-title">Vocational Training</h4>
              <p class="detail-text">
                Skill-based training programs for youth (15-30 years) including tailoring, carpentry,
                IT basics, and other trade skills.
              </p>
              <ul class="feature-list">
                <li>6-12 month programs</li>
                <li>Placement assistance</li>
                <li>Tool kits provided</li>
                <li>Certification</li>
              </ul>
            </div>

            <div class="detail-item">
              <div class="detail-icon">👩‍💻</div>
              <h4 class="detail-title">Digital Literacy</h4>
              <p class="detail-text">
                Computer basics and digital skills training to bridge the digital divide and prepare
                communities for the modern workforce.
              </p>
              <ul class="feature-list">
                <li>Basic computer skills</li>
                <li>Internet training</li>
                <li>MS Office courses</li>
                <li>Online safety</li>
              </ul>
            </div>
          </div>
        </div>

        <!-- Healthcare Services -->
        <div class="service-block">
          <div class="service-header">
            <div class="service-icon-large">⚕️</div>
            <h3 class="service-heading">Healthcare & Wellness</h3>
          </div>
          <p class="service-intro">
            We work to ensure accessible, quality healthcare for all members of the communities we serve.
          </p>

          <div class="service-details-grid">
            <div class="detail-item">
              <div class="detail-icon">🏥</div>
              <h4 class="detail-title">Health Camps & Screening</h4>
              <p class="detail-text">
                Regular health camps in communities providing free medical checkups, basic treatments,
                and health awareness.
              </p>
              <ul class="feature-list">
                <li>Free medical consultations</li>
                <li>Health screening</li>
                <li>First aid training</li>
                <li>Medicine provision</li>
              </ul>
            </div>

            <div class="detail-item">
              <div class="detail-icon">👶</div>
              <h4 class="detail-title">Maternal & Child Health</h4>
              <p class="detail-text">
                Comprehensive programs focused on pregnancy care, safe delivery support, immunization,
                and child nutrition.
              </p>
              <ul class="feature-list">
                <li>Prenatal care</li>
                <li>Safe delivery support</li>
                <li>Immunization programs</li>
                <li>Nutrition counseling</li>
              </ul>
            </div>

            <div class="detail-item">
              <div class="detail-icon">💊</div>
              <h4 class="detail-title">Medicine Access Program</h4>
              <p class="detail-text">
                Ensuring access to essential and affordable medicines for chronic and acute conditions
                through subsidized programs.
              </p>
              <ul class="feature-list">
                <li>Affordable medicines</li>
                <li>Prescription support</li>
                <li>Treatment guidance</li>
                <li>Follow-up care</li>
              </ul>
            </div>

            <div class="detail-item">
              <div class="detail-icon">🧠</div>
              <h4 class="detail-title">Health Awareness Programs</h4>
              <p class="detail-text">
                Community education on hygiene, sanitation, disease prevention, nutrition, and mental health.
              </p>
              <ul class="feature-list">
                <li>Hygiene campaigns</li>
                <li>Disease prevention</li>
                <li>Nutrition education</li>
                <li>Mental health support</li>
              </ul>
            </div>
          </div>
        </div>

        <!-- Economic Empowerment Services -->
        <div class="service-block">
          <div class="service-header">
            <div class="service-icon-large">💼</div>
            <h3 class="service-heading">Economic Empowerment</h3>
          </div>
          <p class="service-intro">
            We enable individuals to achieve financial independence and sustainable livelihoods.
          </p>

          <div class="service-details-grid">
            <div class="detail-item">
              <div class="detail-icon">💰</div>
              <h4 class="detail-title">Microfinance Programs</h4>
              <p class="detail-text">
                Access to small loans for entrepreneurship and small business development with
                minimal collateral requirements.
              </p>
              <ul class="feature-list">
                <li>Low-interest loans</li>
                <li>Flexible repayment</li>
                <li>Business support</li>
                <li>Financial literacy</li>
              </ul>
            </div>

            <div class="detail-item">
              <div class="detail-icon">🚀</div>
              <h4 class="detail-title">Entrepreneurship Training</h4>
              <p class="detail-text">
                Comprehensive training in business planning, marketing, financial management, and
                operational excellence.
              </p>
              <ul class="feature-list">
                <li>Business planning</li>
                <li>Market research</li>
                <li>Financial management</li>
                <li>Marketing basics</li>
              </ul>
            </div>

            <div class="detail-item">
              <div class="detail-icon">👩‍🏫</div>
              <h4 class="detail-title">Women's Economic Initiative</h4>
              <p class="detail-text">
                Special programs focusing on women's economic independence through self-help groups
                and cooperative enterprises.
              </p>
              <ul class="feature-list">
                <li>Self-help groups</li>
                <li>Collective enterprises</li>
                <li>Market access</li>
                <li>Rights awareness</li>
              </ul>
            </div>

            <div class="detail-item">
              <div class="detail-icon">🤝</div>
              <h4 class="detail-title">Market Linkage Program</h4>
              <p class="detail-text">
                Connecting small producers directly with markets, reducing intermediaries and increasing
                their profit margins.
              </p>
              <ul class="feature-list">
                <li>Direct market access</li>
                <li>Quality standards</li>
                <li>Fair pricing</li>
                <li>Supply chain support</li>
              </ul>
            </div>
          </div>
        </div>

        <!-- Environmental Services -->
        <div class="service-block">
          <div class="service-header">
            <div class="service-icon-large">🌱</div>
            <h3 class="service-heading">Environmental Conservation</h3>
          </div>
          <p class="service-intro">
            We promote sustainable practices that protect our environment for future generations.
          </p>

          <div class="service-details-grid">
            <div class="detail-item">
              <div class="detail-icon">🌳</div>
              <h4 class="detail-title">Reforestation Projects</h4>
              <p class="detail-text">
                Large-scale tree planting initiatives to restore forests, improve air quality, and
                combat climate change.
              </p>
              <ul class="feature-list">
                <li>Native tree species</li>
                <li>Community participation</li>
                <li>Long-term monitoring</li>
                <li>Employment creation</li>
              </ul>
            </div>

            <div class="detail-item">
              <div class="detail-icon">💧</div>
              <h4 class="detail-title">Water & Sanitation</h4>
              <p class="detail-text">
                Installation of clean water systems and sanitation facilities to improve public
                health and reduce waterborne diseases.
              </p>
              <ul class="feature-list">
                <li>Water harvesting systems</li>
                <li>Toilet construction</li>
                <li>Hygiene training</li>
                <li>Maintenance support</li>
              </ul>
            </div>

            <div class="detail-item">
              <div class="detail-icon">♻️</div>
              <h4 class="detail-title">Waste Management Solution</h4>
              <p class="detail-text">
                Community-based waste management programs focusing on segregation, recycling, and
                sustainable disposal methods.
              </p>
              <ul class="feature-list">
                <li>Waste segregation</li>
                <li>Recycling programs</li>
                <li>Composting initiatives</li>
                <li>Community education</li>
              </ul>
            </div>

            <div class="detail-item">
              <div class="detail-icon">🌍</div>
              <h4 class="detail-title">Climate Action Programs</h4>
              <p class="detail-text">
                Initiatives promoting renewable energy adoption, climate resilience, and sustainable
                agricultural practices.
              </p>
              <ul class="feature-list">
                <li>Renewable energy</li>
                <li>Climate awareness</li>
                <li>Sustainable farming</li>
                <li>Disaster preparedness</li>
              </ul>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- Service Process Section -->
    <section class="process-section">
      <div class="process-container">
        <h2 class="section-title">How We Deliver Services</h2>

        <div class="process-steps">
          <div class="process-step">
            <div class="step-number">1</div>
            <h3 class="step-title">Assessment</h3>
            <p class="step-description">
              We conduct thorough needs assessments in communities to understand specific challenges
              and requirements.
            </p>
          </div>

          <div class="process-step">
            <div class="step-number">2</div>
            <h3 class="step-title">Planning</h3>
            <p class="step-description">
              We develop customized plans in collaboration with community members and local leaders
              to ensure relevance and sustainability.
            </p>
          </div>

          <div class="process-step">
            <div class="step-number">3</div>
            <h3 class="step-title">Implementation</h3>
            <p class="step-description">
              Our experienced team implements programs with quality standards and community
              participation at every step.
            </p>
          </div>

          <div class="process-step">
            <div class="step-number">4</div>
            <h3 class="step-title">Monitoring</h3>
            <p class="step-description">
              We regularly track progress, measure impact, and make adjustments to ensure programs
              remain effective.
            </p>
          </div>

          <div class="process-step">
            <div class="step-number">5</div>
            <h3 class="step-title">Evaluation</h3>
            <p class="step-description">
              We conduct comprehensive evaluations to document outcomes, share learning, and improve
              future interventions.
            </p>
          </div>
        </div>
      </div>
    </section>

    <!-- Call to Action -->
    <section class="cta-section">
      <div class="cta-container">
        <h2 class="cta-title">Need Our Services?</h2>
        <p class="cta-text">
          Contact us to learn more about our programs and how we can support your community.
        </p>
        <RouterLink to="/contact" class="cta-button">Get in Touch</RouterLink>
      </div>
    </section>
  </div>
</template>

<style scoped>
.services {
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

/* Main Services Section */
.main-services-section {
  padding: 4rem 2rem;
  background-color: white;
}

.services-container {
  max-width: 1200px;
  margin: 0 auto;
}

.service-block {
  margin-bottom: 4rem;
  padding-bottom: 3rem;
  border-bottom: 2px solid #e2e8f0;
}

.service-block:last-child {
  border-bottom: none;
}

.service-header {
  display: flex;
  align-items: center;
  gap: 2rem;
  margin-bottom: 2rem;
}

.service-icon-large {
  font-size: 4rem;
  flex-shrink: 0;
}

.service-heading {
  font-size: 2rem;
  font-weight: 700;
  color: #1e293b;
  margin: 0;
}

.service-intro {
  font-size: 1.1rem;
  color: #555;
  margin-bottom: 2rem;
  max-width: 800px;
  line-height: 1.8;
}

.service-details-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
  gap: 2rem;
}

.detail-item {
  background-color: #f8f9fa;
  padding: 2rem;
  border-radius: 8px;
  transition: all 0.3s ease;
}

.detail-item:hover {
  background-color: white;
  box-shadow: 0 8px 20px rgba(0, 0, 0, 0.1);
  transform: translateY(-5px);
}

.detail-icon {
  font-size: 2.5rem;
  margin-bottom: 1rem;
}

.detail-title {
  font-size: 1.2rem;
  font-weight: 600;
  color: #1e293b;
  margin-bottom: 1rem;
}

.detail-text {
  font-size: 0.95rem;
  color: #555;
  margin-bottom: 1.5rem;
  line-height: 1.6;
}

.feature-list {
  list-style: none;
  padding: 0;
  display: flex;
  flex-direction: column;
  gap: 0.75rem;
}

.feature-list li {
  font-size: 0.9rem;
  color: #555;
  padding-left: 1.5rem;
  position: relative;
}

.feature-list li::before {
  content: '✓';
  position: absolute;
  left: 0;
  color: #42b983;
  font-weight: bold;
  font-size: 1.1rem;
}

/* Process Section */
.process-section {
  padding: 4rem 2rem;
  background-color: #f8f9fa;
}

.process-container {
  max-width: 1200px;
  margin: 0 auto;
}

.process-steps {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
  gap: 1.5rem;
}

.process-step {
  background-color: white;
  padding: 2rem;
  border-radius: 8px;
  text-align: center;
  position: relative;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.1);
  transition: all 0.3s ease;
}

.process-step:hover {
  transform: translateY(-8px);
  box-shadow: 0 12px 24px rgba(0, 0, 0, 0.15);
}

.step-number {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  width: 50px;
  height: 50px;
  background: linear-gradient(135deg, #43e97b 0%, #38f9d7 100%);
  color: white;
  font-size: 1.5rem;
  font-weight: 700;
  border-radius: 50%;
  margin-bottom: 1rem;
}

.step-title {
  font-size: 1.2rem;
  font-weight: 600;
  color: #1e293b;
  margin-bottom: 1rem;
}

.step-description {
  font-size: 0.95rem;
  color: #555;
  line-height: 1.6;
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

/* Responsive Design */
@media (max-width: 768px) {
  .header-title {
    font-size: 2rem;
  }

  .service-header {
    flex-direction: column;
    align-items: flex-start;
  }

  .service-heading {
    font-size: 1.5rem;
  }

  .section-title {
    font-size: 2rem;
  }

  .service-details-grid {
    grid-template-columns: 1fr;
  }

  .process-steps {
    grid-template-columns: repeat(auto-fit, minmax(150px, 1fr));
  }

  .main-services-section,
  .process-section,
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

  .service-icon-large {
    font-size: 3rem;
  }

  .service-heading {
    font-size: 1.25rem;
  }

  .detail-title {
    font-size: 1.1rem;
  }

  .cta-title {
    font-size: 1.75rem;
  }

  .process-steps {
    grid-template-columns: 1fr;
  }
}
</style>
