<template>
  <section class="trust-badges">
    <div class="trust-badges__container">
      <div v-for="(badge, index) in badges" :key="index" class="trust-badge">
        <div class="trust-badge__icon">
          <img :src="badge.icon" :alt="badge.title" />
        </div>
        <h3 class="trust-badge__title">{{ badge.title }}</h3>
        <p class="trust-badge__description">{{ badge.description }}</p>
      </div>
    </div>
  </section>
</template>

<script setup>
const badges = [
  {
    icon: "/images/delivery.png",
    title: "Free Delivery",
    description:
      "Australia wide free delivery on all orders straight from our warehouse.",
  },
  {
    icon: "/images/help.png",
    title: "Need Help?",
    description:
      "We’re always here for you if you have any questions or to help with your purchase.",
  },
  {
    icon: "/images/shop.png",
    title: "Shop with confidence",
    description:
      "All transactions 100% secure and your purchase is covered by our buyers Protection.",
  },
];
</script>

<style lang="scss" scoped>
.trust-badges {
  padding: 40px 20px;
  background-color: #fff;

  &__container {
    display: flex;
    justify-content: space-between;
    align-items: center;
    gap: 20px;
    max-width: 1200px;
    margin: 0 auto;

    @media (max-width: 768px) {
      flex-direction: column;
      gap: 30px;
    }
  }

  .trust-badge {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    text-align: center;
    flex: 1;
    padding: 20px;
    border-right: 1px solid #ddd;

    &:last-child {
      border-right: none;
    }

    &__icon {
      margin-bottom: 15px;

      img {
        width: 50px;
        height: 50px;
        object-fit: contain;
      }
    }

    &__title {
      font-size: 18px;
      font-weight: bold;
      margin-bottom: 10px;
      color: #333;
    }

    &__description {
      font-size: 14px;
      color: #666;
      line-height: 1.5;
    }
  }
}
</style>