<template>
  <article class="education-card">
    <header class="education-card__header">
      <div class="education-card__logo-wrapper">
        <img
          :src="`img/educations/${data.logo}`"
          :alt="data.title"
          class="education-card__logo"
        />
      </div>
      <h3 class="education-card__title">
        {{ data.title }}
      </h3>
    </header>
    <div class="education-card__body">
      <span class="education-card__fac">
        {{ data.faculty }}
      </span>
      <span class="education-card__year">{{ data.year }}</span>
      <span class="education-card__percent">
        <span>Percentage</span>
        - {{ data.percentage }}
      </span>
    </div>
  </article>
</template>

<script>
export default {
  props: {
    data: {
      type: Object,
      require: true
    }
  }
};
</script>

<style lang="scss" scoped>
.education-card {
  padding: 16px 24px;
  background-color: #f7f9fc;
  &__header {
    display: flex;
    align-items: center;
    gap: 16px;
    margin-bottom: 8px;
  }

  &__logo-wrapper {
    width: 50px;
    height: 50px;
  }

  &__logo {
    width: 100%;
    height: 100%;
    object-fit: contain;
  }

  &__title {
    color: var(--gray-darker);
    font-size: 12px;
    font-weight: 500;
    line-height: 16px;
  }

  &__body {
    display: flex;
    flex-direction: column;
    gap: 2px;
    font-weight: 400;
    color: var(--gray-default);
  }

  &__fac {
    color: var(--gray-darker);
    font-size: 14px;
    font-weight: 500;
    line-height: 18px;
  }

  &__year {
    font-size: 10px;
    letter-spacing: 0.101px;
  }

  &__percent {
    font-size: 12px;
    letter-spacing: 0.121px;

    span {
      color: var(--iris-100);
    }
  }
}
</style>
