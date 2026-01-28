<template>
  <section class="article-carousel">
    <UCarousel
      v-slot="{ item }"
      :items="items"
      arrows
      dots
      loop
      :ui="{ item: 'basis-1/2 ', root: 'w-[900px]', base: 'w-[800px]  ' }"
    >
      <div class="carousal-items">
        <img :src="item.image" :alt="item.alt" class="carousal-items_left" />
        <div class="carousal-items_right">
          <h1>{{ item.title }}</h1>
          <p>{{ item.description }}</p>
        </div>
      </div>
    </UCarousel>
  </section>
</template>
<script setup>
const items = ref([
  {
    image: "https://picsum.photos/468/468?random=1",
    title: "The Modern Stress Epidemic: Why Minimalist Wellness is the Answer",
    description:
      "Stress has become an unavoidable part of modern life. From endless to-do lists to the...read more.",
    alt: "image1",
  },
  {
    image: "https://picsum.photos/468/468?random=2",
    title:
      "Space-Saving Solutions Made Stylish for Modern Australian Homes in 2025",
    description:
      "In 2025, Australian homeowners are redefining how they live by embracing innovative solutions that make...read more.					",
  },
  {
    image: "https://picsum.photos/468/468?random=3",
    title:
      "Outdoor Design Tips for a Minimal yet Functional Backyard Oasis in 2025",
    description:
      "Imagine stepping into your backyard, only to find a cluttered, chaotic space that feels more...read more.					",
  },
  {
    image: "https://picsum.photos/468/468?random=4",
    title:
      "How Floor Sofas and Rolling Egg Storage Units Are Revolutionising Modern Living",
    description:
      "In the fast-paced world of 2025, finding the perfect balance between style, comfort, and practicality...read more.					",
  },
  {
    image: "https://picsum.photos/468/468?random=5",
    title:
      "Affordable Designer Lighting and Clever Kitchen Products to Elevate Your Home",
    description:
      "Affordable Designer Lighting and Clever Kitchen Products to Elevate Your Home In today’s world, creating...read more.					",
  },
  {
    image: "https://picsum.photos/468/468?random=6",
    title: "What Is Quiet Luxury? How It Aligns with Minimalist Living",
    description:
      "Quiet luxury brings elegance to your home through quality over flash. This design philosophy focuses...read more.					",
  },
]);
</script>

<style lang="scss" scoped>
.article-carousel {
  height: auto;
  display: flex;
  justify-content: center;
  align-items: center;
  padding: 50px;
  background-color: white;
}

.carousal-items {
  padding: 10px;
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  gap: 10px;
  border: 1px solid rgb(191, 179, 179);
  border-radius: 5px;
  color: black;

  &_left {
    width: 200px;
    height: 200px;
  }

  &_right {
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    align-items: center;
  }
}
</style>
