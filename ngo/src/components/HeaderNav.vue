<script setup lang="ts">
import { RouterLink } from 'vue-router'
</script>

<template>
  <header class="header">
    <div class="header-container">
      <!-- Logo -->
      <div class="logo-section">
        <img alt="NGO Logo" class="logo" src="@/assets/logo.svg" />
      </div>

      <!-- Navigation -->
      <nav class="nav-menu">
        <RouterLink to="/" class="nav-link">Home</RouterLink>
        <RouterLink to="/about" class="nav-link">About Us</RouterLink>
        <RouterLink to="/services" class="nav-link">Our Services</RouterLink>
        <RouterLink to="/contact" class="nav-link">Contact Us</RouterLink>
      </nav>
    </div>
  </header>
</template>

<style scoped>
.header {
  background-color: #fff;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.1);
  position: sticky;
  top: 0;
  z-index: 100;
}

.header-container {
  display: flex;
  align-items: center;
  justify-content: space-between;
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 2rem;
  height: 80px;
}

.logo-section {
  flex-shrink: 0;
}

.logo {
  height: 60px;
  width: auto;
}

.nav-menu {
  display: flex;
  align-items: center;
  gap: 2rem;
  margin: 0;
  padding: 0;
  list-style: none;
}

.nav-link {
  text-decoration: none;
  color: #333;
  font-weight: 500;
  font-size: 1rem;
  padding: 0.5rem 1rem;
  border-radius: 4px;
  transition: all 0.3s ease;
  position: relative;
}

.nav-link:hover {
  color: var(--color-primary, #42b983);
  background-color: rgba(66, 185, 131, 0.1);
}

.nav-link.router-link-active {
  color: var(--color-primary, #42b983);
  font-weight: 600;
  border-bottom: 2px solid var(--color-primary, #42b983);
}

@media (max-width: 768px) {
  .header-container {
    flex-wrap: wrap;
    height: auto;
    padding: 1rem 1.5rem;
  }

  .logo-section {
    width: 100%;
    text-align: center;
    margin-bottom: 1rem;
  }

  .logo {
    height: 50px;
  }

  .nav-menu {
    width: 100%;
    justify-content: center;
    gap: 1rem;
    flex-wrap: wrap;
  }

  .nav-link {
    font-size: 0.9rem;
    padding: 0.4rem 0.8rem;
  }
}

@media (max-width: 480px) {
  .nav-menu {
    gap: 0.5rem;
  }

  .nav-link {
    font-size: 0.8rem;
    padding: 0.4rem 0.6rem;
  }

  .logo {
    height: 40px;
  }
}
</style>
