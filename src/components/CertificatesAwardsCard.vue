<template>
  <article class="card">
    <div class="card__img-wrapper">
      <img :src="`img/certificates-awards/${data.icon}`" alt="" class="card__img">
    </div>
    <div class="card__text-wrapper">
      <span class="card__pre-title">
        {{ data.preTitle }}
      </span>
      <h3 class="card__title">
        {{ data.title }}
      </h3>
    </div>
    <span class="card__year">
      {{ data.year }}
    </span>
  </article>
</template>

<script>

  export default {
    props: {
      data: {
        type: Object,
        require: true,
        validator(val) {
          return Object.keys(val).includes('year') && 
            Object.keys(val).includes('title') && 
            Object.keys(val).includes('preTitle') && 
            Object.keys(val).includes('icon');
        }
      }
    }
  }
</script>

<style lang="scss" scoped>
.card {
  padding: 15px 24px;
  display: flex;
  gap: 12px;

  @media(max-width: 576px) {
    padding: 10px;
  }

  &__img-wrapper {
    width: 43px;
    height: 43px;
  }

  &__img {
    width: 100%;
    height: 100%;
    object-fit: contain;
  }

  &__text-wrapper {
    display: flex;
    flex-direction: column;
  }

  &__pre-title {
    margin-bottom: auto;
    color: var(--gray-default);
    font-size: 13.604px;
    font-weight: 400;
    line-height: 17.491px; /* 128.571% */
    letter-spacing: 0.136px;
  }

  &__title {
    margin: 0;
    font-size: 13px;
    font-weight: 400;
    line-height: 17.491px; /* 128.571% */
    letter-spacing: 0.136px;
  }
  
  &__year {
    margin-left: auto;
    color: var(--gray-dark);
    font-size: 11.661px;
    font-weight: 400;
    line-height: 15.548px; /* 133.333% */
    letter-spacing: 0.117px;
  }
}
</style>