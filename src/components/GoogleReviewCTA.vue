<template>
  <section class="review-cta-section py-5">
    <div class="container">
      <div class="review-box shadow-lg" data-aos="zoom-in">
        
        <div class="row align-items-center">
          
          <div class="col-md-8 text-center text-md-start mb-4 mb-md-0">
            <div class="d-flex align-items-center justify-content-center justify-content-md-start mb-2">
              <svg xmlns="http://www.w3.org/2000/svg" width="32" height="32" viewBox="0 0 48 48" class="me-3">
                <path fill="#EA4335" d="M24 9.5c3.54 0 6.71 1.22 9.21 3.6l6.85-6.85C35.9 2.38 30.47 0 24 0 14.62 0 6.51 5.38 2.56 13.22l7.98 6.19C12.43 13.72 17.74 9.5 24 9.5z"/>
                <path fill="#4285F4" d="M46.98 24.55c0-1.57-.15-3.09-.38-4.55H24v9.02h12.94c-.58 2.96-2.26 5.48-4.78 7.18l7.73 6c4.51-4.18 7.09-10.36 7.09-17.65z"/>
                <path fill="#FBBC05" d="M10.53 28.59c-.48-1.45-.76-2.99-.76-4.59s.27-3.14.76-4.59l-7.98-6.19C.92 16.46 0 20.12 0 24c0 3.88.92 7.54 2.56 10.78l7.97-6.19z"/>
                <path fill="#34A853" d="M24 48c6.48 0 11.93-2.13 15.89-5.81l-7.73-6c-2.15 1.45-4.92 2.3-8.16 2.3-6.26 0-11.57-4.22-13.47-9.91l-7.98 6.19C6.51 42.62 14.62 48 24 48z"/>
              </svg>
              <h3 class="fw-bold m-0 text-white">Love our service?</h3>
            </div>
            
            <p class="text-white-50 mb-0 ps-md-5 ms-md-2">
              Your reviews help neighbors find reliable waste solutions. 
              <br class="d-none d-lg-block">
              We'd appreciate a moment of your time!
            </p>
          </div>

          <div class="col-md-4 text-center text-md-end">
            <a :href="googleLink" target="_blank" class="btn btn-gold btn-lg rounded-pill pulse-animation">
              <i class="fas fa-star me-2"></i> Review Us on Google
            </a>
          </div>

        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: 'GoogleReviewCTA',
  data() {
    return {
      // REPLACE THIS LINK with your actual Google Business Review Link
      // To get it: Search your business on Google > Click "Get more reviews" > Copy link
      googleLink: 'https://www.google.com/search?client=ms-android-verizon-us-rvc3&sca_esv=40f8f7d9d6eddcc8&si=AMgyJEtREmoPL4P1I5IDCfuA8gybfVI2d5Uj7QMwYCZHKDZ-E0YYq__5sD1Eo8cAxcHmx_XC16yGTuCqGwSYF3XmvYDyk0aygIo8FP6nKBORkkzN6SB-dS7aeTImmznNSwDdCkAqMkUMcSb6a65NSHvpdlAMfgui9Q%3D%3D&q=24/7+Trash+Solutions+LLC+Reviews&sa=X&ved=2ahUKEwiK0vn7t7SRAxWzg4kEHTh3HgUQ0bkNegQIIBAE&biw=1920&bih=945&dpr=1' 
    }
  }
}
</script>

<style scoped>
.review-cta-section {
  /* Using a dark neutral background so the colors pop */
  background-color: #f8f9fa; 
}

.review-box {
  /* Using your Primary Red for the background card */
  background: linear-gradient(135deg, #71141c 0%, #4a0d12 100%);
  border-radius: 15px;
  padding: 40px;
  position: relative;
  overflow: hidden;
  border: 1px solid rgba(255,255,255,0.1);
}

/* Optional: Add a subtle background pattern or effect */
.review-box::before {
  content: '"';
  position: absolute;
  top: -20px;
  right: 20px;
  font-size: 150px;
  color: rgba(255, 255, 255, 0.05);
  font-family: serif;
  line-height: 1;
}

/* Custom Button Styling */
.btn-gold {
  background-color: #d4af37;
  color: #71141c; /* Red Text on Gold Button */
  font-weight: 800;
  border: none;
  padding: 15px 30px;
  transition: all 0.3s ease;
}

.btn-gold:hover {
  background-color: #fff; /* Turns white on hover */
  color: #71141c;
  transform: translateY(-3px);
  box-shadow: 0 10px 20px rgba(0,0,0,0.2);
}

/* Pulse Animation to grab attention */
@keyframes pulse {
  0% { box-shadow: 0 0 0 0 rgba(212, 175, 55, 0.7); }
  70% { box-shadow: 0 0 0 15px rgba(212, 175, 55, 0); }
  100% { box-shadow: 0 0 0 0 rgba(212, 175, 55, 0); }
}

.pulse-animation {
  animation: pulse 2s infinite;
}
</style>