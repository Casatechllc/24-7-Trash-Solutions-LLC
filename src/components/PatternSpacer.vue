<template>
  <div class="spacer-wrapper mt-3">
    <div class="accent-bar"></div>

    <div class="tiled-trapezoid"></div>
  </div>
</template>

<script>
export default {
  name: 'PatternSpacer'
}
</script>

<style scoped>
/* 1. Wrapper to handle spacing */
.spacer-wrapper {
  position: relative;
  width: 100%;
  height: 120px; /* Adjust height of the spacer here */
  margin-top: -50px; /* Optional: Pulls it up to overlap slightly if needed */
  z-index: 10;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: flex-end; /* Aligns shape to bottom */
}

/* 2. The Gold Accent Line */
.accent-bar {
  width: 25%; /* Starts smaller than the trapezoid */
  height: 6px;
  background-color: var(--color-accent); /* Your Gold Accent */
  border-radius: 3px;
  margin-bottom: -3px; /* Tucks it slightly onto the shape */
  z-index: 2;
  box-shadow: 0 0 10px rgba(212, 175, 55, 0.5); /* Glowing effect */
  position: relative;
  top: 98%;
}

/* 3. The Tiled Trapezoid */
.tiled-trapezoid {
  width: 100%;
  height: 100%;
  
  /* THE SHAPE: 
     20% 0 = Top Left (starts in)
     80% 0 = Top Right (starts in)
     100% 100% = Bottom Right (full width)
     0% 100% = Bottom Left (full width)
  */
  clip-path: polygon(100% 0, 0 0, 20% 100%, 80% 100%);
  
  /* THE COLOR: Your Primary Red */
  background-color: var(--color-primary); 

  /* THE TILE PATTERN: Diagonal stripes */
  background-image: repeating-linear-gradient(
    45deg,
    rgba(255, 255, 255, 0.05), /* Very subtle lighter stripe */
    rgba(255, 255, 255, 0.05) 10px,
    transparent 10px,
    transparent 20px
  );

  background-attachment: fixed;

}

/* Mobile Adjustment: Make the top wider on phones so it doesn't look too pointy */
@media (max-width: 768px) {
  .tiled-trapezoid {
    clip-path: polygon(0 0, 100% 0, 100% 100%, 0% 100%); /* Becomes a rectangle on mobile */
    /* OR use this for a subtle angle on mobile: */
    /* clip-path: polygon(10% 0, 90% 0, 100% 100%, 0% 100%); */
  }
  
  .accent-bar {
    width: 50%;
  }
  
  .spacer-wrapper {
    height: 80px;
  }
}
</style>