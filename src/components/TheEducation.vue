<template>
  <section class="education">
    <section-title>
      Education
    </section-title>
    <ul class="education__list list-reset">
      <li
        class="education__item"
        v-for="education in educations"
        :key="education.id"
      >
        <EducationCard :data="education" />
      </li>
    </ul>
  </section>
</template>

<script>
import educationsData from '@/db/educations';
import EducationCard from '@/components/EducationCard.vue';
import SectionTitle from '@/components/UI/SectionTitle.vue';

export default {
  components: { EducationCard, SectionTitle },
  data() {
    return {
      educations: educationsData
    };
  }
};
</script>

<style lang="scss" scoped>
.education {
  padding-left: 32px;
  overflow: hidden;
  
  &__list {
    display: grid;
    grid-template-columns: 225px;
    grid-auto-flow: column;
    grid-auto-columns: 225px;
    gap: 8px;
    overflow: auto;

    &::-webkit-scrollbar {
        display: none;
      }
      /* Скрываем scrollbar для IE, Edge и Firefox */
    -ms-overflow-style: none;  /* IE и Edge */
    scrollbar-width: none;  /* Firefox */

    li > * {
      height: 100%;
    }
  }
}
</style>
