<template>
  <header class="header">
    <div class="header-inner">
      <!-- Left Section: Logo -->
      <div class="header-inner_left">
        <NuxtLink to="/">
          <img :src="logoUrl" class="header-inner_left--logo" alt="logo" />
        </NuxtLink>
      </div>

      <!-- Center Section: Navigation Links -->
      <nav class="header-inner_center">
        <NuxtLink
          v-for="nav in navList"
          :key="nav.id"
          class="navigation-links"
          :to="nav.link"
        >
          {{ nav.label }}
        </NuxtLink>
      </nav>

      <!-- Right Section: Wishlist, Login, and Cart -->
      <div class="header-inner_right">
        <NuxtLink to="/wishlist" class="header-inner_right--link">
          <i class="fas fa-heart"></i> WISHLIST<svg
            xmlns="http://www.w3.org/2000/svg"
            fill="none"
            viewBox="0 0 24 24"
            stroke-width="1.5"
            stroke="currentColor"
            class="size-6"
          >
            <path
              stroke-linecap="round"
              stroke-linejoin="round"
              d="M21 8.25c0-2.485-2.099-4.5-4.688-4.5-1.935 0-3.597 1.126-4.312 2.733-.715-1.607-2.377-2.733-4.313-2.733C5.1 3.75 3 5.765 3 8.25c0 7.22 9 12 9 12s9-4.78 9-12Z"
            />
          </svg>
        </NuxtLink>
        <NuxtLink to="/login" class="header-inner_right--link">
          LOGIN
        </NuxtLink>
        <NuxtLink to="/cart" class="header-inner_right--cart">
          <UButton
            trailing-icon="i-lucide-shopping-cart"
            :ui="{
              base: 'p-[15px] flex items-center justify-center bg-black hover:bg-green-600 rounded-[90px] text-white w-[160px]',
            }"
          >
            CART / $0.00</UButton
          >
          <!-- <i class="fas fa-shopping-bag"></i> CART / $0.00 -->
        </NuxtLink>
      </div>
    </div>
  </header>
</template>

<script setup>
import { ref } from "vue";

const logoUrl = ref("/images/logo-white.png");

const navList = [
  { id: 1, label: "Lighting", link: "/lighting" },
  { id: 2, label: "Indoor Design", link: "/indoor-design" },
  { id: 3, label: "Kitchen Must Haves", link: "/kitchen-must-haves" },
  { id: 4, label: "Contact", link: "/contact" },
];
</script>

<style lang="scss" scoped>
@import "~/assets/css/colors.scss";

.header {
  position: relative;
  display: flex;
  justify-content: center;
  align-items: center;
  background-color: transparent;
  padding: 20px 50px;
  background-color: rgb(240, 238, 238);
  .header-inner {
    display: flex;
    flex-direction: row;
    justify-content: space-between;
    align-items: center;
    gap: 80px;

    &_left {
      width: 150px;

      &--logo {
        height: 50px;
        object-fit: contain;
      }
    }

    &_center {
      display: flex;
      flex-direction: row;
      justify-content: center;
      gap: 30px;

      .navigation-links {
        font-size: 14px;
        font-weight: 600;
        color: $header_nav_text_color;
        text-decoration: none;
        text-transform: uppercase;
        transition: color 0.3s ease;

        &:hover {
          color: $header_nav_text_color_hover;
        }
      }
    }

    &_right {
      display: flex;
      align-items: center;
      gap: 20px;

      &--link {
        font-size: 14px;
        text-decoration: none;
        display: flex;
        align-items: center;
        font-weight: 600;
        gap: 5px;
        color: $header_nav_text_color;

        &:hover {
          color: $header_nav_text_color_hover;
        }
      }

      &--cart {
        font-size: 14px;
        color: white;
        text-decoration: none;
        background-color: black;

        border-radius: 20px;
        display: flex;
        align-items: center;
        gap: 5px;

        &:hover {
          background-color: #333;
        }
      }
    }
  }
}
</style>
