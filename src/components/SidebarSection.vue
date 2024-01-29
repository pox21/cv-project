<template>
  <section class="sidebar-section">
    <h2 v-if="title.trim()" class="sidebar-section__title">{{ title }}</h2>
    <SectionItem :content="item" v-for="item in contents" :key="item.id" />
  </section>
</template>

<script>
import SectionItem from './SectionItem.vue';

export default {
    props: {
        title: {
            type: String,
            default: "",
        },
        contents: {
            type: Array,
            required: true,
        },
    },
    components: { SectionItem }
};
</script>

<style lang="scss" scoped>
.sidebar-section {
  padding-top: 32px;
  padding-bottom: 32px;
  display: flex;
  flex-direction: column;
  gap: 24px;

  &__title {
    margin: 0;
    color: var(--gray-default);
    font-size: 12px;
    font-weight: 400;
    line-height: 16px; /* 133.333% */
    letter-spacing: 0.121px;
  }
}
</style>
