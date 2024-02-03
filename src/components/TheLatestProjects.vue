<template>
  <section class="latest-project">
    <section-title> Latest projects </section-title>
    <ul class="latest-project__list list-reset">
      <li class="latest-project__item" v-for="item in latestProject" :key="item.id">
        <LatestProjectCard :project="item" />
      </li>
    </ul>
  </section>
</template>

<script>
import latestProjectData from '@/db/latestProject';
import SectionTitle from '@/components/UI/SectionTitle.vue';
import LatestProjectCard from '@/components/LatestProjectCard.vue';
export default {
  components: { SectionTitle, LatestProjectCard },
  data() {
    return {
      latestProject: latestProjectData
    }
  }
};
</script>

<style lang="scss" scoped>

.latest-project {

  &__list {
    border-radius: 8px;
    display: flex;
    flex-wrap: wrap;
    gap: 12px;
    overflow: hidden;
  }

  &__item {
    display: flex;
    flex-direction: column;
    background-color: var(--sidebar-bg-color);
  }
}


</style>
