<script>
import { Collapse } from 'bootstrap'; // Import Bootstrap Collapse for mobile menu handling

export default {
  name: 'Navbar',
  data() {
    return {
      phone: '(540) 849-5594',
      isScrolled: false
    }
  },
  computed: {
    phoneClean() {
      return this.phone.replace(/\D/g, '');
    }
  },
  mounted() {
    window.addEventListener('scroll', this.handleScroll);
  },
  unmounted() {
    window.removeEventListener('scroll', this.handleScroll);
  },
  methods: {
    handleScroll() {
      // Useful if you want to change transparency on scroll later
      this.isScrolled = window.scrollY > 50;
    },
    closeMenu() {
      // Closes the mobile menu when a link is clicked
      const navbarCollapse = document.getElementById('navbarNav');
      if (navbarCollapse.classList.contains('show')) {
        const bsCollapse = new Collapse(navbarCollapse, {
          toggle: false
        });
        bsCollapse.hide();
      }
    }
  }
}
</script>

<template>
  <nav class="navbar navbar-expand-lg navbar-dark fixed-top custom-navbar" :class="{ 'scrolled': isScrolled }">
    <div class="container">
      <a class="navbar-brand fw-bold" href="#home" @click="closeMenu">
        <!-- <i class="fas fa-trash-alt me-2"></i> -->
        24/7 Trash Solutions LLC
      </a>

      <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarNav" aria-controls="navbarNav" aria-expanded="false" aria-label="Toggle navigation">
        <span class="navbar-toggler-icon"></span>
      </button>

      <div class="collapse navbar-collapse" id="navbarNav">
        <ul class="navbar-nav ms-auto align-items-center">
          <li class="nav-item">
            <a class="nav-link" href="#home" @click="closeMenu">Home</a>
          </li>
          <li class="nav-item">
            <a class="nav-link" href="#about" @click="closeMenu">About</a>
          </li>
          <li class="nav-item">
            <a class="nav-link" href="#services" @click="closeMenu">Services</a>
          </li>
          <li class="nav-item">
            <a class="nav-link" href="#pricing" @click="closeMenu">Pricing</a>
          </li>
          
          <li class="nav-item ms-lg-3 mt-3 mt-lg-0">
            <a :href="'tel:' + phoneClean" class="btn btn-gold rounded-pill px-4">
              <i class="fas fa-phone me-2"></i> {{ phone }}
            </a>
          </li>
        </ul>
      </div>
    </div>
  </nav>
</template>

<style scoped>
.custom-navbar {
  background-color: var(--color-primary); /* Brand Red */
  box-shadow: 0 2px 10px rgba(0,0,0,0.3);
  padding-top: 0.8rem;
  padding-bottom: 0.8rem;
  transition: all 0.3s ease;
  /* width: 100vw; */
}

.navbar-brand {
  font-family: var(--font-family-headings);
  font-size: 1.5rem;
  color: var(--light-text) !important;
  letter-spacing: 0.5px;
}

.nav-link {
  color: rgba(255, 255, 255, 0.9) !important;
  font-weight: 500;
  margin-right: 15px;
  transition: color 0.3s ease;
  font-family: var(--font-family-body);
}

.nav-link:hover {
  color: var(--color-accent) !important; /* Gold hover effect */
}

/* Specific Gold Button for Navbar */
.btn-gold {
  background-color: var(--color-accent);
  color: var(--color-primary);
  font-weight: 700;
  border: none;
  transition: all 0.3s ease;
}

.btn-gold:hover {
  background-color: #fff;
  color: var(--color-primary);
  transform: translateY(-2px);
}

/* Mobile Adjustments */
@media (max-width: 991px) {
  .navbar-collapse {
    background-color: var(--color-primary);
    padding: 1rem;
    border-radius: 0 0 10px 10px;
    border-top: 1px solid rgba(255,255,255,0.1);

    max-height: 80vh; 
    overflow-y: auto;
  }
  
  .nav-item {
    margin-bottom: 10px;
  }
}

/* Extra Small Screens (Android Phones) */
@media (max-width: 400px) {
  /* Shrink the text slightly so "24/7 Trash Solutions LLC" fits next to the button */
  .navbar-brand {
    font-size: 1.1rem; 
  }
}
</style>