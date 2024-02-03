<template>
  <article class="achievements-card">
    <div class="achievements-card__wrapper">
      <div class="achievements-card__head">
        <span class="achievements-card__icon">
          <TitleCircleBlack />
        </span>
        <span class="achievements-card__year">{{ achievement.year }}</span>
        <span class="achievements-card__location">
          <inline-svg src="img/icons/location.svg" ></inline-svg>
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
      require: true,
      validator(val) {
        return Object.keys(val).includes('year') && 
        Object.keys(val).includes('location') && 
        Object.keys(val).includes('logo') && 
        Object.keys(val).includes('title') && 
        Object.keys(val).includes('subtitle') && 
        Object.keys(val).includes('desc');
      }
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

  @media(max-width: 576px) {
    display: flex;
    flex-direction: column;
  }

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
