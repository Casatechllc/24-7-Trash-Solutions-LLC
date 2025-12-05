<script>
export default {
  name: 'Footer',
  data() {
    return {
      currentYear: new Date().getFullYear(),
      phone1: '(540) 849-5594',
      phone2: '(540) 560-4528',
      email: '247trashsolutions@gmail.com',
      facebookUrl: 'https://www.facebook.com/profile.php?id=61577914419017',
      casatechUrl: 'https://casatechllc.com',
      googleUrl: 'https://share.google/UP1IDOxfrwAmtFTn3'
    }
  },
  computed: {
    phone1Clean() { return this.phone1.replace(/\D/g, ''); },
    phone2Clean() { return this.phone2.replace(/\D/g, ''); }
  }
}
</script>

<template>
  <footer class="footer text-white pt-5 pb-3">
    <div class="container">
      <div class="row">
        
        <div class="col-md-6 mb-4">
          <h4 class="text-uppercase fw-bold mb-3 footer-title">24/7 Trash Solutions LLC</h4>
          <p class="small text-white-50 pe-md-5">
            Prompt, efficient, and reliable waste management services tailored for residential, commercial, and industrial spaces.
          </p>
          <div class="mt-3">
            <a :href="facebookUrl" target="_blank" class="social-icon">
              <i class="fab fa-facebook-f"></i>
            </a>
            <a :href="googleUrl" target="_blank" class="social-icon ms-2">
              <i class="fas fa-share-alt"></i>
            </a>
          </div>
          <p class="mt-3 text-warning fst-italic">
            <i class="fas fa-language me-1"></i> Se habla español
          </p>
        </div>

        <div class="col-md-6 mb-4">
          <h5 class="fw-bold mb-3 footer-title">Contact Us</h5>
          <ul class="list-unstyled text-white-50">
            <li class="mb-3 d-flex">
              <i class="fas fa-phone-alt mt-1 me-3 text-danger"></i>
              <div>
                <a :href="'tel:' + phone1Clean" class="d-block text-white text-decoration-none">{{ phone1 }}</a>
                <a :href="'tel:' + phone2Clean" class="d-block text-white text-decoration-none">{{ phone2 }}</a>
              </div>
            </li>
            <li class="mb-3 d-flex">
              <i class="fas fa-envelope mt-1 me-3 text-danger"></i>
              <a :href="'mailto:' + email" class="text-white text-decoration-none">{{ email }}</a>
            </li>
            <li class="d-flex">
              <i class="fas fa-map-marker-alt mt-1 me-3 text-danger"></i>
              <span class="small">
                Harrisonburg, Staunton, Waynesboro, Stuarts Draft, Charlottesville, Rockingham & Augusta County.
              </span>
            </li>
          </ul>
        </div>
      </div>

      <hr class="border-secondary my-4">

      <div class="row align-items-center">
        <div class="col-md-6 text-center text-md-start">
          <p class="small mb-0 text-white-50">
            &copy; {{ currentYear }} 24/7 Trash Solutions LLC. All rights reserved. 
            <span class="d-none d-sm-inline">|</span> 
            <br class="d-sm-none">
            Powered by <a :href="casatechUrl" target="_blank" class="casatech-link">Casatech LLC</a>
          </p>
        </div>
        <div class="col-md-6 text-center text-md-end mt-3 mt-md-0">
          <p class="small mb-0 text-white-50">
            <i class="fas fa-clock text-warning me-1"></i> Open 24 Hours, 7 Days a Week
          </p>
        </div>
      </div>
    </div>
  </footer>
</template>

<style scoped>
.footer {
  background-color: var(--color-secondary); /* Black */
  border-top: 5px solid var(--color-primary); /* Red Border at top */
}

.footer-title {
  color: var(--color-primary);
  letter-spacing: 1px;
}

.social-icon {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  width: 40px;
  height: 40px;
  background-color: #333;
  color: #fff;
  border-radius: 50%;
  text-decoration: none;
  transition: all 0.3s ease;
}

.social-icon:hover {
  background-color: var(--color-primary);
  color: #fff;
  transform: translateY(-3px);
}

/* Specific Style for Casatech Link */
.casatech-link {
  color: var(--color-accent); /* Using Gold Accent */
  font-weight: 700;
  text-decoration: none;
  transition: color 0.3s ease;
}

.casatech-link:hover {
  color: #fff;
  text-decoration: underline;
}
</style>