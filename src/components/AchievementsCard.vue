<template>
  <article class="achievements-card">
    <div class="achievements-card__wrapper">
      <div class="achievements-card__head">
        <span class="achievements-card__icon">
          <TitleCircleBlack />
        </span>
        <span class="achievements-card__year">{{ achievement.year }}</span>
        <span class="achievements-card__location">
          <svg
            width="13"
            height="13"
            viewBox="0 0 13 13"
            fill="none"
            xmlns="http://www.w3.org/2000/svg"
          >
            <path
              d="M6.52861 11.046C5.89176 10.5028 5.30146 9.90728 4.76388 9.26566C3.95714 8.30212 2.99915 6.86714 2.99915 5.49973C2.99843 4.07158 3.85844 2.78375 5.17787 2.2372C6.49729 1.69064 8.01606 1.99308 9.02545 3.00339C9.68922 3.66421 10.0611 4.56311 10.0581 5.49973C10.0581 6.86714 9.10007 8.30212 8.29334 9.26566C7.75576 9.90728 7.16546 10.5028 6.52861 11.046ZM6.52861 3.9871C5.9882 3.9871 5.48884 4.27541 5.21864 4.74342C4.94843 5.21142 4.94843 5.78803 5.21864 6.25604C5.48884 6.72405 5.9882 7.01236 6.52861 7.01236C7.36401 7.01236 8.04123 6.33513 8.04123 5.49973C8.04123 4.66433 7.36401 3.9871 6.52861 3.9871Z"
              fill="#79819A"
            />
          </svg>
          {{ achievement.location }}
        </span>
      </div>
      <div class="achievements-card__info">
        <div class="achievements-card__logo-wrapper">
          <img
            :src="`img/achievements/${achievement.logo}`"
            :alt="achievement.title"
            class="achievements-card__logo"
          />
        </div>
        <div class="achievements-card__info-wrapper">
          <span class="achievements-card__subtitle">{{ achievement.subtitle }}</span>
          <h3 class="achievements-card__title">{{ achievement.title }}</h3>
        </div>
      </div>
    </div>
    <p class="achievements-card__desc">
      {{ achievement.desc }}
    </p>
  </article>
</template>

<script>
import TitleCircleBlack from '@/components/UI/TitleCircleBlack.vue';
export default {
  components: {
    TitleCircleBlack
  },
  props: {
    achievement: {
      type: Object,
      require: true
    }
  }
};
</script>

<style lang="scss" scoped>
.achievements-card {
  position: relative;
  padding-left: 40px;
  display: grid;
  grid-template-columns: 240px 1fr;
  gap: 8px;

  &__head {
    display: flex;
    align-items: center;
    gap: 4px;
    margin-bottom: 10px;
  }

  &__icon {
    position: absolute;
    left: 0;
    display: block;
    width: 24px;
    height: 24px;
    border-radius: 100%;
    background-color: #fff;
    box-shadow: 0px 2.017px 2.017px 0px rgba(0, 0, 0, 0.04) inset,
      0px 12.101px 48.404px 0px rgba(0, 0, 0, 0.04),
      0px 2.017px 8.067px 0px rgba(0, 0, 0, 0.05);
    overflow: hidden;
    z-index: 1;

    svg {
      width: 100%;
      height: 100%;
      object-fit: cover;
    }
  }

  &__year {
    color: var(--gray-dark);
    font-size: 10px;
    font-weight: 400;
    letter-spacing: 0.101px;
  }

  &__location {
    display: inline-flex;
    align-items: center;
    gap: 4px;
    color: var(--gray-default);
    font-size: 10px;
    letter-spacing: 0.101px;
  }

  &__subtitle {
    color: var(--gray-default);
    font-size: 12.101px;
    line-height: 16px; /* 133.333% */
    letter-spacing: 0.121px;
  }

  &__title {
    margin: 0;
    color: var(--gray-darker);
    font-size: 14px;
    font-weight: 500;
    line-height: 18px;
  }

  &__info {
    display: flex;
    align-items: center;
    gap: 16px;
  }

  &__logo-wrapper {
    width: 50px;
    height: 50px;
    overflow: hidden;
  }

  &__logo {
    width: 100%;
    height: 100%;
    object-fit: contain;
  }

  &__info-wrapper {
    display: flex;
    flex-direction: column;
    gap: 4px;
  }

  &__desc {
    margin: 0;
    color: var(--gray-default);
    font-size: 12px;
    font-weight: 400;
    letter-spacing: 0.121px;
  }
}
</style>
