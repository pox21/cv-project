<template>
  <article class="card">
    <div class="card__wrapper">
      <div class="card__img-wrapper">
        <img :src="`img/latest-projects/${project.icon}`" alt="" class="card__img">
      </div>
      <div class="card__text-wrapper">
        <h3 class="card__title">{{ project.title }}</h3>
        <p class="card__descr">
          {{ project.text }}
        </p>
      </div>
    </div>
    <a href="#" target="_blank" class="card__link">
      <span class="card__link-icon">
        <inline-svg src="img/icons/link.svg" />
      </span>
      <span class="card__link-text">
        {{ project.link }}
      </span>
    </a>
  </article>
</template>

<script>
  export default {
    props: {
      project: {
        type: Object,
        require: true,
        validator(val) {
          return Object.keys(val).includes('icon') && 
            Object.keys(val).includes('title') && 
            Object.keys(val).includes('text') && 
            Object.keys(val).includes('link');
        }
      }
    }
  }
</script>

<style lang="scss" scoped>
.card {
  display: flex;
  flex-direction: column;
  flex-grow: 1;
  max-width: 339px;
  padding: 24px;
  background-color: inherit;

  @media(max-width: 576px) {
    padding: 10px;
  }

  &__wrapper {
    display: flex;
    gap: 16px;
    margin-bottom: 2px;
  }

  &__img-wrapper {
    width: 48px;
    height: 48px;
  }

  &__img {
    width: 100%;
    height: 100%;
    object-fit: contain;
  }

  &__title {
    margin-top: 0;
    margin-bottom: 4px;
    color: var(--gray-darker);
    font-size: 16px;
    font-weight: 500;
    line-height: 20px; 
  }

  &__descr {
    margin: 0;
    color: var(--gray-default);
    font-size: 14px;
    font-weight: 400;
    line-height: 18px; 
    letter-spacing: 0.141px;
  }

  &__link {
    margin-top: auto;
    display: flex;
    align-items: center;
    gap: 12px;
  }

  &__link-icon {
    display: flex;
    align-items: center;
    justify-content: center;
    width: 24px;
    height: 24px;
    border-radius: 100%;
    background-color: #e1e7fe;
  }

  &__link-text {
    color: var(--Secondary-Default, #516CF7);
    font-family: 'Outfit';
    font-size: 16.135px;
    font-style: normal;
    font-weight: 600;
    line-height: 20.168px; /* 125% */
    text-decoration: underline;
    overflow-wrap: anywhere;
  }
}
</style>