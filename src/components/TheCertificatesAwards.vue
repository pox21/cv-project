<template>
  <section class="certificates-awards">
    <section-title> Certificates & Awards </section-title>
    <ul class="certificates-awards__list list-reset">
      <li class="certificates-awards__item">
        <article class="card">
          <div class="card__img-wrapper">
            <img src="/img/certificates-awards/web-design.png" alt="" class="card__img">
          </div>
          <div class="card__text-wrapper">
            <span class="card__pre-title">
              freeCodeCamp
            </span>
            <h3 class="card__title">
              Responsive Web Design
            </h3>
          </div>
          <span class="card__year">
            Dec 2021 - Feb 2022
          </span>
        </article>
      </li>
      <li class="certificates-awards__item">
        <article class="card">
          <div class="card__img-wrapper">
            <img src="/img/certificates-awards/google.svg" alt="" class="card__img">
          </div>
          <div class="card__text-wrapper">
            <span class="card__pre-title">
              Data Strcture & Algorithms
            </span>
            <h3 class="card__title">
              Google
            </h3>
          </div>
          <span class="card__year">
            Mar 2021 - Jun 2021
          </span>
        </article>
      </li>
    </ul>
  </section>
</template>

<script>
import SectionTitle from '@/components/UI/SectionTitle.vue';
export default {
  components: { SectionTitle }
};
</script>

<style lang="scss" scoped>

.certificates-awards {

  &__list {
    display: grid;
    grid-template-columns: 1fr;
    gap: 8px;
    border-radius: 8px;
    overflow: hidden;
  }

  &__item {
    background-color: var(--sidebar-bg-color);
  }
}

.card {
  padding: 15px 24px;
  display: flex;
  gap: 12px;

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
