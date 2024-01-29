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
    grid-template-columns: 228px;
    grid-auto-flow: column;
    grid-auto-columns: 228px;
    gap: 8px;
    overflow: auto;

    li > * {
      height: 100%;
    }
  }
}
</style>
