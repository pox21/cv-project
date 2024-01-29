<template>
  <a :href="content.link" class="sidebar-item">
    <BaseIcon class="sidebar-item__icon" :iconName="content.icon" />
    <span class="sidebar-item__wrapper">
      <span class="sidebar-item__title">
        {{ content.title }}
      </span>
      <span v-if="content.link" class="sidebar-item__link">
        {{ content.text }}
      </span>
      <span v-else="content.text" class="sidebar-item__text">
        {{ content.text }}
      </span>
    </span>
  </a>
</template>

<script>
import BaseIcon from "@/components/BaseIcon.vue";

export default {
  props: {
    content: {
      type: Object,
      required: true,
    },
  },
  components: { BaseIcon },
};
</script>

<style lang="scss" scoped>
.sidebar-item {
  display: flex;
  align-items: center;
  gap: 16px;

  &:not(:has(.sidebar-item__link)) {
    pointer-events: none;
  }

  &__icon {
    flex-shrink: 0;
  }

  &__wrapper {
    display: flex;
    flex-direction: column;
    gap: 4px;
    word-break: break-all;
  }

  &__title {
    color: var(--gray-default);
    font-size: 12px;
    font-weight: 400;
    line-height: 16px; /* 133.333% */
    letter-spacing: 0.121px;
  }

  &__text, &__link {
    color: var(--gray-dark);
    font-size: 14px;
    font-weight: 500;
    line-height: 18px;
  }

  &:hover {
    .sidebar-item__link {
      text-decoration: underline;
    }
  }
}
</style>
