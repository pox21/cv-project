<template>
  <section class="tools-skills">
    <section-title> Tools/Skills </section-title>
    <ul class="tools-skills__list list-reset">
      <li class="tools-skills__item" v-for="skill in skills" :key="skill.id">
        <ToolsSkillsCard :data="skill" />
      </li>
    </ul>
  </section>
</template>
<script>
import skillsData from '@/db/skills';
import SectionTitle from '@/components/UI/SectionTitle.vue';
import ToolsSkillsCard from '@/components/ToolsSkillsCard.vue';
export default {
  components: { SectionTitle, ToolsSkillsCard },
  data() {
    return {
      skills: skillsData
    };
  }
};
</script>

<style lang="scss" scoped>
.tools-skills {
  
  &__list {
    display: flex;
    flex-wrap: wrap;
    gap: 8px;
    border-radius: 8px;
    overflow: hidden;
  }

  &__item {
    display: flex;
    flex-direction: column;
    justify-content: center;

    background-color: var(--sidebar-bg-color);
    flex-basis: 19%;
  }

  &__item:first-child, &__item:nth-child(2), &__item:nth-child(3) {
    min-height: 130px;
    flex-basis: 32.5%;
  }
}
</style>
