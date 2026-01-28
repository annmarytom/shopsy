<template>
  <section class="about-masonry">
    <UContainer class="about-masonry__container">
      <div class="about-masonry__grid">
        <!-- Left top: About card -->
        <div class="about-masonry__aboutCard">
          <h2 class="about-masonry__title">ABOUT MADE MINIMAL</h2>

          <p class="about-masonry__desc">
            At Made Minimal, our aim is to provide designer furniture and
            products at affordable prices. We are Brisbane based team who have
            traveled the world and partnered with manufacturers to bring
            beautiful contemporary and modern furniture and products to the
            Australian market.
          </p>

          <UButton
            to="/shop"
            size="sm"
            variant="solid"
            class="about-masonry__cta"
            :ui="{
              base:
                'rounded-none bg-transparent hover:bg-transparent text-white ' +
                'border border-white/70 hover:border-white ' +
                'px-6 py-2 tracking-widest font-semibold',
            }"
          >
            SHOP NOW
          </UButton>
        </div>

        <!-- Right: Big image -->
        <div class="about-masonry__bigImage">
          <img
            class="about-masonry__img"
            src="/images/about1.png"
            alt="Featured product"
            loading="lazy"
          />
        </div>

        <!-- Bottom left images -->
        <div class="about-masonry__smallLeft">
          <img
            class="about-masonry__img"
            src="/images/about2.png"
            alt="Product 1"
            loading="lazy"
          />
        </div>

        <div class="about-masonry__smallRight">
          <img
            class="about-masonry__img"
            src="/images/about3.jpg"
            alt="Product 2"
            loading="lazy"
          />
        </div>
      </div>
    </UContainer>
  </section>
</template>

<style scoped lang="scss">
.about-masonry {
  padding: 28px 0;
  background-color: white;
  &__container {
    width: 100%;
  }

  &__grid {
    display: grid;
    grid-template-columns: 1fr 1.1fr; // left + right
    grid-template-rows: 280px 240px; // top row + bottom row
    gap: 22px;
  }

  &__aboutCard {
    grid-column: 1 / 2;
    grid-row: 1 / 2;
    background: #2b2b2b;
    color: #fff;
    padding: 44px 36px;
    display: flex;
    flex-direction: column;
    justify-content: center;
    text-align: center;
  }

  &__title {
    margin: 0;
    font-size: 34px;
    letter-spacing: 0.04em;
    font-weight: 800;
  }

  &__desc {
    margin: 14px auto 0;
    max-width: 680px;
    font-size: 14px;
    line-height: 1.7;
    opacity: 0.9;
  }

  &__cta {
    margin: 22px auto 0;
  }

  &__bigImage {
    grid-column: 2 / 3;
    grid-row: 1 / 3;
    overflow: hidden;
    background: #f3f3f3;
  }

  &__smallLeft {
    grid-column: 1 / 2;
    grid-row: 2 / 3;
    overflow: hidden;
    background: #f3f3f3;
  }

  &__smallRight {
    grid-column: 1 / 2;
    grid-row: 2 / 3;
    overflow: hidden;
    background: #f3f3f3;
  }

  &__grid {
    grid-template-areas:
      "about big"
      "small1 big";
  }

  &__aboutCard {
    grid-area: about;
  }
  &__bigImage {
    grid-area: big;
  }

  // bottom row becomes two items side-by-side in left column
  &__smallRow {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 22px;
  }

  // We'll override by wrapping bottom images using :deep? -> simpler: use grid directly:
  &__smallLeft {
    grid-column: 1 / 2;
    grid-row: 2 / 3;
  }
  &__smallRight {
    grid-column: 1 / 2;
    grid-row: 2 / 3;
  }
}
</style>
