<template>
  <article class="card">
    <div class="card__img-wrapper">
      <img :src="`img/tools-skills/${data.icon}`" :alt="data.title" class="card__img">
    </div>
    <h3 class="card__title">{{ data.title }}</h3>
    <p class="card__descr">{{ data.description }}</p>
  </article>
</template>

<script>
export default {
  props: {
    data: {
      type: Object,
      require: true,
      validator(val) {
        return Object.keys(val).includes('icon') && 
          Object.keys(val).includes('title') && 
          Object.keys(val).includes('description');
      }
    }
  }
}
</script>

<style lang="scss" scoped>
.card {
  padding: 6px;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  text-align: center;
  background-color: var(--sidebar-bg-color);

  &__img-wrapper {
    margin-bottom: 8px;
    max-height: 60px;
    max-width: 60px;
    overflow: hidden;
  }
  
  &__img {
    height: 100%;
    width: 100%;
    object-fit: contain;
  }

  &__title {
    margin-top: 0;
    margin-bottom: 2px;
    font-size: 14px;
    font-weight: 500;
    line-height: 18px;
    color: var(--gray-darker);
  }

  &__descr {
    margin: 0;
    color: var(--gray-default);
    font-size: 10px;
    font-weight: 400;
    line-height: normal;
    letter-spacing: 0.101px;
  }
}
</style>