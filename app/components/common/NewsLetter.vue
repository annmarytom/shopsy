<template>
  <section class="news-letter-section">
    <div class="newsletter-inner">
      <div class="newsletter-inner_left">
        <h2>Signup for Newsletter</h2>
      </div>
      <div class="newsletter-inner_center">
        <UInput
          type="text"
          placeholder="Email Address"
          :ui="{
            root: 'text-black',
            base: 'w-[500px] h-[50px] bg-white  border-0 border-gray-300 ',
          }"
        ></UInput>
        <div class="re-captche">
          <div class="re-captche_checkbox">
            <UCheckbox
              label="I'am not a robot"
              required
              :ui="{ base: 'w-[20px] h-[20px] text-black-500' }"
            ></UCheckbox>
          </div>
          <div class="re-captche_text">
            <img
              src="/images/captche.png"
              :style="{ width: '30px', height: '30px' }"
            />
            <p>reCAPTCHE</p>
            <p>Privacy-Terms</p>
          </div>
        </div>
      </div>
      <div class="newsletter-inner-right">
        <UButton
          type="submit"
          :ui="{
            base: 'w-[150px] h-[50px] bg-black text-white-600 p-[10px] flex items-center justify-center cursor-pointer hover:bg-black',
          }"
        >
          SUBSCRIBE</UButton
        >
      </div>
    </div>
  </section>
</template>

<script setup></script>
<style lang="scss" scoped>
.news-letter-section {
  display: flex;
  justify-content: center;
  align-items: center;
  height: auto;
  background-color: rgb(212, 201, 201);
}

.newsletter-inner {
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  align-items: center;
  gap: 30px;
  padding: 40px;

  &_left {
    margin-right: 50px;
    font-size: 14px;
    font-family: "Open Sans", sans-serif;
    color: black;
    font-weight: 700;
    letter-spacing: 0.05em;
    text-transform: uppercase;
    line-height: 1.5;
    letter-spacing: 2px;
  }

  &_center {
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    gap: 20px;

    .re-captche {
      width: 300px;
      display: flex;
      flex-direction: row;
      justify-content: space-between;
      align-items: center;
      height: auto;
      padding: 10px;
      border: 1px solid gray;
      background-color: white;

      &_checkbox {
        display: flex;
        justify-content: space-between;
        flex-direction: row;
        gap: 20px;
      }

      &_text {
        display: flex;
        flex-direction: column;
        justify-content: space-between;
        font-size: 10px;
        color: rgb(77, 76, 76);
      }
    }
  }
}
</style>
