<script>
import AOS from 'aos';
import 'aos/dist/aos.css';

export default {
  name: 'HomeView',
  data() {
    return {
      phone1: '(540) 849-5594',
      phone2: '(540) 560-4528',
      email: '247trashsolutions@gmail.com',
      locations: [
        'Harrisonburg, VA',
        'Staunton, VA',
        'Waynesboro, VA',
        'Stuarts Draft, VA',
        'Charlottesville, VA',
        'Rockingham County',
        'Augusta County'
      ],
      faq: [
        {
          question: "What types of payments do you accept?",
          answer: "We accept most major credit cards, cash, and checks. Please contact us for specific payment arrangement details."
        },
        {
          question: "Do you offer services on weekends?",
          answer: "Yes! As our name suggests, we are 24/7 Trash Solutions. We offer services Monday through Sunday, around the clock."
        },
        {
          question: "How do I book a dumpster?",
          answer: "Booking is simple. You can call or text us at (540) 849-5594, or email us. We'll discuss your needs and schedule a drop-off time."
        },
        {
          question: "What can I put in the 13 Yard Dumpster?",
          answer: "You can dispose of general household trash, construction debris, yard waste, and furniture. Hazardous materials, tires, and batteries are typically prohibited—please ask if you are unsure."
        }
      ]
    }
  },
  computed: {
    phone1Clean() {
      return this.phone1.replace(/\D/g, '');
    },
    // Used if you add a second call button
    phone2Clean() {
      return this.phone2.replace(/\D/g, '');
    }
  },
  mounted() {
    AOS.init({
      duration: 800,
      once: true,
      offset: 100
    });
  }
}
</script>

<template>
  <main>
    <!-- Hero Section -->
    <section id="home" class="hero">
        <div class="container" data-aos="fade-up">
            <h1 class="display-4 fw-bold">Efficient. Reliable. <span class="hero-highlight">24/7.</span></h1>
            <p class="lead mb-4">Prompt waste management services tailored for residential, commercial, and industrial spaces.</p>
            <div class="d-flex gap-3 justify-content-center flex-wrap">
                <a :href="'tel:' + phone1Clean" class="btn btn-custom btn-lg"><i class="fas fa-phone-alt me-2"></i> Call Now</a>
                <a href="#contact" class="btn btn-outline-custom btn-lg text-white" style="border-color: #f8f9fa;">Book Service</a>
            </div>
            <p class="mt-4 fst-italic"><i class="fas fa-language"></i> Se habla español tambien</p>
        </div>
    </section>

    <!-- About Section -->
    <section id="about" class="section-padding">
        <div class="container">
            <div class="row align-items-center">
                <div class="col-lg-6" data-aos="fade-right">
                    <img src="/images/about-us.jpg" alt="Clean Environment" class="about-img mb-4 mb-lg-0">
                </div>
                <div class="col-lg-6" data-aos="fade-left">
                    <h2 class="mb-4">About Us</h2>
                    <p class="lead">We take care of all your trashy problems with prompt, efficient, and reliable waste management services.</p>
                    <p>
                        Our dedicated team is committed to maintaining the cleanliness and hygiene of your residential, commercial, or industrial spaces, ensuring a healthier environment and peace of mind. We pride ourselves on exceptional customer service, environmentally responsible disposal methods, and flexible scheduling tailored to meet your unique needs.
                    </p>
                    <p>
                        We also offer convenient Dumpster Rental Services & Debris Removal to support projects of any size. Contact us today for a free quote and discover how 24/7 Trash Solutions LLC can provide the waste management solutions you deserve.
                    </p>
                    <div class="mt-4">
                        <div class="d-flex align-items-center mb-2">
                            <i class="fas fa-check-circle text-success me-2"></i> <span>Prompt & Efficient</span>
                        </div>
                        <div class="d-flex align-items-center mb-2">
                            <i class="fas fa-check-circle text-success me-2"></i> <span>Environmentally Responsible</span>
                        </div>
                        <div class="d-flex align-items-center">
                            <i class="fas fa-check-circle text-success me-2"></i> <span>Flexible Scheduling</span>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Services Section -->
    <section id="services" class="section-padding position-relative overflow-hidden">
        
        <div class="video-background">
            <div class="video-overlay" style="background-color: rgba(255, 255, 255, 0.9);"></div>
        </div>

        <div class="container position-relative" style="z-index: 2;">
            <div class="text-center mb-5" data-aos="fade-up">
                <h2>Our Services</h2>
                <div style="width: 60px; height: 4px; background: var(--color-primary); margin: 10px auto;"></div>
                <p>Comprehensive solutions for all your disposal and organization needs</p>
            </div>

            <div class="row g-4">
                <div class="col-md-6 col-lg-3" data-aos="fade-up" data-aos-delay="100">
                    <div class="service-card text-center">
                        <div class="service-icon"><i class="fas fa-trash"></i></div>
                        <h3 class="h4">Trash Removal</h3>
                        <p class="small">Regular or one-time removal services ensuring your property stays clean and hygienic.</p>
                    </div>
                </div>

                <div class="col-md-6 col-lg-3" data-aos="fade-up" data-aos-delay="200">
                    <div class="service-card text-center">
                        <div class="service-icon"><i class="fas fa-truck-loading"></i></div>
                        <h3 class="h4">Dumpster Rental</h3>
                        <p class="small">Convenient rentals (13-Yard) for construction, renovation, or large cleanout projects.</p>
                    </div>
                </div>

                <div class="col-md-6 col-lg-3" data-aos="fade-up" data-aos-delay="300">
                    <div class="service-card text-center">
                        <div class="service-icon"><i class="fas fa-recycle"></i></div>
                        <h3 class="h4">Debris Collection</h3>
                        <p class="small">Specialized collection for yard waste, construction debris, and bulk items.</p>
                    </div>
                </div>

                <div class="col-md-6 col-lg-3" data-aos="fade-up" data-aos-delay="400">
                    <div class="service-card text-center">
                        <div class="service-icon"><i class="fas fa-boxes"></i></div>
                        <h3 class="h4">Organize & Declutter</h3>
                        <p class="small">Professional sorting and organization to help you reclaim space in your garage or home.</p>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Details/Pricing Section -->
    <section id="pricing" class="section-padding">
        <div class="container">
            <h2 class="text-center mb-5 fw-bold" data-aos="fade-up">Pricing / Precios</h2>
            
            <div class="row g-4">
                
                <div class="col-lg-6" data-aos="fade-right">
                    <div class="dumpster-card h-100 d-flex flex-column">
                        <div class="card-body p-4 p-md-5">
                            <h3 class="fw-bold mb-1">Dumpster Rental</h3>
                            <p class="text-warning mb-4 fw-bold">13-Yard Container</p>
                            
                            <div class="d-flex align-items-baseline mb-4">
                                <span class="display-3 fw-bold me-2">$350</span>
                                <span class="h5 fw-normal text-white-50">Flat Rate</span>
                            </div>

                            <ul class="list-unstyled lead mb-4 flex-grow-1">
                                <li class="mb-2"><i class="fas fa-check-circle text-warning me-2"></i> Drop-off & Pickup Included</li>
                                <li class="mb-2"><i class="fas fa-calendar-alt text-warning me-2"></i> 5-Day Rental Period</li>
                                <li class="mb-2"><i class="fas fa-weight-hanging text-warning me-2"></i> 1 Ton of Waste Included</li>
                            </ul>

                            <div class="extras-box p-3 rounded mb-4">
                                <p class="mb-1"><strong>Extra Days:</strong> $5/day (after 5th day)</p>
                                <p class="mb-1"><strong>Swap-out:</strong> $180 (Empty & Return)</p>
                                <p class="mb-0"><strong>Overweight:</strong> $90/ton</p>
                            </div>

                            <div class="d-grid gap-2">
                                <a :href="'tel:' + phone1Clean" class="btn btn-light fw-bold text-danger">
                                    <i class="fas fa-phone-alt me-2"></i> Call Now
                                </a>
                                <a :href="'sms:' + phone1Clean" class="btn btn-outline-light">
                                    <i class="fas fa-comment-dots me-2"></i> Text Us
                                </a>
                            </div>
                        </div>
                    </div>
                </div>

                <div class="col-lg-6" data-aos="fade-left">
                    <div class="dumpster-card h-100 d-flex flex-column position-relative overflow-hidden">
                        
                        <div class="ribbon-wrapper">
                            <div class="ribbon">Se Habla Español</div>
                        </div>

                        <div class="card-body p-4 p-md-5">
                            <h3 class="fw-bold mb-1">Renta de Contenedor</h3>
                            <p class="text-warning mb-4 fw-bold">Tamaño de 13 Yardas</p>
                            
                            <div class="d-flex align-items-baseline mb-4">
                                <span class="display-3 fw-bold me-2">$350</span>
                                <span class="h5 fw-normal text-white-50">Precio Fijo</span>
                            </div>

                            <ul class="list-unstyled lead mb-4 flex-grow-1">
                                <li class="mb-2"><i class="fas fa-check-circle text-warning me-2"></i> Entrega y Recogida Incluida</li>
                                <li class="mb-2"><i class="fas fa-calendar-alt text-warning me-2"></i> Renta de 5 Días</li>
                                <li class="mb-2"><i class="fas fa-weight-hanging text-warning me-2"></i> 1 Tonelada de Basura Incluida</li>
                            </ul>

                            <div class="extras-box p-3 rounded mb-4">
                                <p class="mb-1"><strong>Días Extra:</strong> $5/día (después del 5to día)</p>
                                <p class="mb-1"><strong>Cambio:</strong> $180 (Vaciar y Devolver)</p>
                                <p class="mb-0"><strong>Peso Extra:</strong> $90/tonelada</p>
                            </div>

                            <div class="d-grid gap-2">
                                <a :href="'tel:' + phone1Clean" class="btn btn-light fw-bold text-danger">
                                    <i class="fas fa-phone-alt me-2"></i> Llamar Ahora
                                </a>
                                <a :href="'sms:' + phone1Clean" class="btn btn-outline-light">
                                    <i class="fas fa-comment-dots me-2"></i> Enviar Texto
                                </a>
                            </div>
                        </div>
                    </div>
                </div>

            </div>
        </div>
    </section>

    <!-- Service Areas -->
    <section class="section-padding position-relative overflow-hidden">
        
        <div class="video-background">
            <video ref="mapVideo" autoplay muted loop playsinline>
                <source src="/images/map-background.mp4" type="video/mp4">
                Your browser does not support the video tag.
            </video>
            <div class="video-overlay"></div>
        </div>

        <div class="container text-center position-relative" style="z-index: 2;">
            <h2 class="mb-4 fw-bold" data-aos="fade-up">Service Areas</h2>
            <p class="mb-5 lead" data-aos="fade-up"><strong>Proudly serving the following locations in Virginia:</strong></p>
            
            <div class="d-flex flex-wrap justify-content-center" data-aos="fade-up">
                <div v-for="location in locations" :key="location" class="location-badge shadow-sm">
                    <i class="fas fa-map-marker-alt me-2 text-danger"></i> {{ location }}
                </div>
            </div>
        </div>
    </section>

    <!-- FAQ Section -->
    <section class="section-padding">
        <div class="container">
            <h2 class="text-center mb-5" data-aos="fade-up">Frequently Asked Questions</h2>
            <div class="row justify-content-center">
                <div class="col-lg-8">
                    <div class="accordion" id="faqAccordion" data-aos="fade-up">
                        <div class="accordion-item" v-for="(item, index) in faq" :key="index">
                            <h2 class="accordion-header" :id="'heading'+index">
                                <button class="accordion-button" :class="{ collapsed: index !== 0 }" type="button" data-bs-toggle="collapse" :data-bs-target="'#collapse'+index">
                                    {{ item.question }}
                                </button>
                            </h2>
                            <div :id="'collapse'+index" class="accordion-collapse collapse" :class="{ show: index === 0 }" data-bs-parent="#faqAccordion">
                                <div class="accordion-body">
                                    {{ item.answer }}
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>
  </main>
</template>

<style scoped>
/* Hero Section */
.hero {
    background: linear-gradient(180deg,rgba(0, 0, 0, 0.71) 50%, rgba(113, 20, 28, 0.85) 100%), 
    url("/images/hero-header.jpg");
    background-size: cover;
    background-position: center;
    background-attachment: fixed; /* <--- THIS LINE creates the static effect */
    height: 100vh;
    display: flex;
    align-items: center;
    justify-content: center;
    text-align: center;
    color: var(--light-text);
}

.hero h1 {
    color: var(--light-text);
    font-size: 3rem;
    margin-bottom: var(--spacing-sm);
}

.hero-highlight {
    color: #d4af37; /* Gold accent */
}

.fa-language {
    color: var(--color-accent);
}

/* About Section */
.section-padding {
    padding: var(--spacing-lg) 0;
}

.bg-light-alt {
    background-color: var(--bg-primary);
}

.about-img {
    border-radius: var(--border-radius);
    box-shadow: var(--box-shadow);
    width: 100%;
    height: 400px;
    object-fit: cover;
}

/* Services Cards */
.service-card {
    background: var(--color-background);
    padding: var(--spacing-md);
    border-radius: var(--border-radius);
    box-shadow: var(--box-shadow);
    height: 100%;
    transition: var(--transition-default);
    border-bottom: 4px solid var(--color-primary);
}

.service-card:hover {
    transform: translateY(-10px);
    box-shadow: 0 10px 20px rgba(0,0,0,0.15);
}

.service-icon {
    font-size: 3rem;
    color: var(--color-primary);
    margin-bottom: var(--spacing-sm);
}

/* Pricing / Details */
.dumpster-details {
    background-color: var(--color-primary);
    color: var(--light-text);
    border-radius: var(--border-radius);
    padding: var(--spacing-lg);
    position: relative;
    overflow: hidden;
}

.dumpster-details h2 {
    color: var(--light-text);
}

.dumpster-card {
    background-color: var(--color-primary);
    color: var(--light-text);
    border-radius: var(--border-radius);
    box-shadow: var(--box-shadow);
    transition: transform 0.3s ease;
    border: 1px solid rgba(255,255,255,0.1);
}

.dumpster-card:hover {
    transform: translateY(-5px);
}

.extras-box {
    background-color: rgba(0, 0, 0, 0.2);
    border: 1px solid rgba(255,255,255,0.2);
    font-size: 0.95rem;
}

/* Ensure the text-warning matches your Gold brand color */
.text-warning {
    color: var(--color-accent) !important; 
}

/* --- Tilted Ribbon Badge Styles --- */
.ribbon-wrapper {
    position: absolute;
    top: 0;
    right: 0;
    width: 150px;
    height: 150px;
    overflow: hidden;
    pointer-events: none; /* Allows clicking through the ribbon area */
}

.ribbon {
    background-color: var(--color-accent); /* Gold */
    color: var(--color-primary); /* Red Text */
    text-transform: uppercase;
    text-align: center;
    font-weight: 800;
    font-size: 0.85rem;
    line-height: 2rem;
    
    /* Rotation magic */
    transform: rotate(45deg);
    position: absolute;
    padding: 2px 0;
    left: -15px;
    top: 35px;
    width: 200px;
    
    box-shadow: 0 5px 10px rgba(0,0,0,0.2);
    border: 1px dashed var(--color-primary); /* Style detail */
}

/* Locations */
/* --- Video Background Styles --- */
.video-background {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    z-index: 1;
}

.video-background video {
    width: 100%;
    height: 100%;
    object-fit: cover;
}

.video-overlay {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    /* White overlay @ 85% opacity so you can see the map moving, but read the text */
    background-color: rgba(255, 255, 255, 0.3); 
}

/* --- Update Location Badges to pop against the video --- */
.location-badge {
    background-color: #ffffff; /* Pure white background */
    color: var(--secondary-dark-grey);
    padding: 10px 20px;
    border-radius: 50px;
    margin: 8px;
    display: inline-block;
    font-weight: 600;
    border: 1px solid rgba(0,0,0,0.1); /* Subtle border */
    transition: transform 0.2s ease;
}

.location-badge:hover {
    transform: translateY(-3px);
    color: var(--color-primary);
    box-shadow: 0 5px 15px rgba(0,0,0,0.1) !important;
}

/* --- FAQ Accordion Customization --- */

/* Default Button State (Collapsed) */
.accordion-button {
    color: var(--color-primary);
    font-weight: 600;
    background-color: #fff;
    box-shadow: none; /* Removes the blue focus glow */
}

/* Active Button State (When clicked/open) */
.accordion-button:not(.collapsed) {
    background-color: var(--color-primary);
    color: white;
    box-shadow: inset 0 -1px 0 rgba(0,0,0,.125);
}

/* Make the arrow white when the button is active */
.accordion-button:not(.collapsed)::after {
    filter: brightness(0) invert(1);
}

/* The answer body area */
.accordion-body {
    background-color: var(--bg-primary); /* Light grey background */
    border: 1px solid rgba(0,0,0,0.1);
    border-top: none;
    color: var(--secondary-dark-grey);
}

/* Add a small border radius adjustment */
.accordion-item {
    border-color: rgba(0,0,0,0.1);
    overflow: hidden;
    margin-bottom: 5px; /* Adds a tiny gap between items */
    border-radius: var(--border-radius) !important;
}

/* Mobile specific */
@media (max-width: 768px) {
    .hero h1 {
        font-size: 2rem;
    }

    /* Turn off the static parallax effect on phones to prevent glitches */
    .hero {
        background-attachment: scroll !important;
    }
    
    /* Ensure the Navbar doesn't get pushed out */
    .navbar-toggler {
        margin-right: 0;
    }
}
</style>