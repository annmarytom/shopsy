<template>
  <UFooter :ui="{ root: 'bg-[#313035]  flex items-center justify-center ' }">
    <div class="footer">
      <div class="footer-upper">
        <div class="footer-upper_left">
          <h1 class=" w-[5cm] border-b-2 border-white p-[15px]">ABOUT US</h1>
          <p>
            Made Minimal is a boutique furniture and lighting store<br />
            located in Brisbane, Australia. Award-winning stylish<br />
            designs at affordable prices.
          </p>
          <div class="meta">
           
            200 Adelaide Street, Brisbane QLD 4000
            info@mademinimal.com.au
          </div>
        </div>

        <div class="footer-upper_right">
          <h2  class=" w-[5cm] border-b-2 border-white p-[15px]">Helpful Links</h2>
          <NuxtLink
            v-for="link in links"
            :key="link.id"
            :to="link.url"
             class=" w-[14cm] border-b-[0.15px] border-white p-[5px]"
          >
            {{ link.name }}
          </NuxtLink>
        </div>
      </div>

      <div class="footer-bottom">
        <div class="footer-bottom_right">
          <h6>Privacy Policy</h6>
          <p>Copyright 2026 © Made Minimal</p>
        </div>
        <div class="footer-bottom_left">
          <UButton
            v-for="card in cards"
            :key="card.id"
            :ui="{
              root: 'w-[100px] h-[40px] bg-[#444] flex items-center justify-center rounded-md',
            }"
            class="payment-button"
          >
            <img :src="card.imageUrl" :alt="card.alt" class="payment-logo" />
          </UButton>
        </div>
      </div>
    </div>
  </UFooter>
</template>

<script setup>
import { ref } from "vue";

const links = ref([
  { id: 1, name: "Shop", url: "https://github.com/annmarytom/shopsy/commits/main/" },
  { id: 2, name: "Refunds & Returns Policy" },
  { id: 3, name: "Payment Methods" },
  { id: 4, name: "Shipping & Delivery" },
  { id: 5, name: "Track your order" },
  { id: 6, name: "NDIS Orders" },
  { id: 7, name: "Write For Us" },
]);

const cards = ref([
  { id: 1, imageUrl: "/images/afterPayCard.png", alt: "Afterpay" },
  { id: 2, imageUrl: "/images/Logo.png", alt: "Paypal" },
  { id: 3, imageUrl: "/images/VisaCard.png", alt: "visa" },
  { id: 4, imageUrl: "/images/master.png", alt: "MasterCard" },
]);
</script>

<style lang="scss" scoped>
.footer {
  padding: 30px;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  gap: 60px;
}

.footer-upper {
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  gap: 70px;

  &_left {
    display: flex;
    flex-direction: column;
 
    gap: 30px;
  }

  &_right {
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    gap: 10px;
  }

  .link-items {
    border-bottom: 1px solid rgba(255, 255, 255, 0.12);
  }
}

.footer-bottom {
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  gap: 400px;

  &_left {
    display: flex;
    gap: 15px;

    .payment-button {
      display: flex;
      align-items: center;
      justify-content: center;
      background-color: #444;
      border-radius: 8px;
      padding: 10px;
      width: 100px;
      height: 50px;

      &:hover {
        background-color: #555;
      }

      .payment-logo {
        width: 60%;
        height: auto;
        object-fit: contain;
      }
    }
  }
}
</style>