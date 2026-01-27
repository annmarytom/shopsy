<template>
  <div class="hero-section">
    <!-- Header -->
    <!-- Hero Content -->
    <div class="hero-content">
      <h1>Stylish designs and products at affordable prices</h1>
      <div class="hero-buttons">
        <NuxtLink to="/indoor-design" class="btn btn-primary"
          >Indoor Design</NuxtLink
        >
        <NuxtLink to="/shop-all" class="btn btn-secondary">Shop All</NuxtLink>
      </div>
    </div>
  </div>
</template>

<script setup></script>

<style lang="scss" scoped>
.hero-section {
  width: 100%;
  height: 100vh;
  background-image: url("/images/homepage-1204x800.jpg");
  background-size: cover;
  background-position: center;
  background-repeat: no-repeat;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  position: relative;

  .hero-content {
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    text-align: center;
    color: white;

    h1 {
      font-size: 4rem;
      font-weight: 500;
      background-color: rgba(
        0,
        0,
        0,
        0.7
      ); /* Black background with transparency */
      display: inline-block;
    }

    .hero-buttons {
      margin-top: 20px;
      display: flex;
      gap: 20px;
      justify-content: center;

      .btn {
        padding: 10px 20px;
        font-size: 16px;
        font-weight: bold;
        text-transform: uppercase;
        border-radius: 5px;
        text-decoration: none;
        display: inline-block;
        transition: all 0.3s ease;

        &.btn-primary {
          background-color: #19e95a;
          color: white;

          &:hover {
            background-color: #218838;
          }
        }

        &.btn-secondary {
          background-color: #000; 
          color: white;

          &:hover {
            background-color: #333;
          }
        }
      }
    }
  }
}
</style>
