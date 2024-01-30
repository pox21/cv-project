<template>
  <h2 class="section-title">
    <span class="section-title__icon">
      <TitleCircle />
    </span>
    <span>
      <slot />
    </span>
  </h2>
</template>

<script>
import TitleCircle from '@/components/UI/TitleCircle.vue';
export default {
  components: { TitleCircle }
};
</script>

<style lang="scss" scoped>
.section-title {
  display: flex;
  align-items: center;
  margin-top: 0;
  margin-bottom: 32px;
  font-family: Outfit;
  font-size: 24.202px;
  font-weight: 500;
  line-height: 32px; /* 133.333% */
  letter-spacing: 0.242px;
  color: var(--gray-darker);

  @media(max-width: 576px) {
    font-size: 21px;
    margin-bottom: 16px;
  }

  &__icon {
    position: absolute;
    left: 0;
    display: block;
    width: 32px;
    height: 32px;
    border-radius: 100%;
    box-shadow: 0px 2.017px 2.017px 0px rgba(0, 0, 0, 0.04) inset,
      0px 12.101px 48.404px 0px rgba(0, 0, 0, 0.04),
      0px 2.017px 8.067px 0px rgba(0, 0, 0, 0.05);
    overflow: hidden;
  }
}
</style>
