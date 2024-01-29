<template>
  <section :class="'asd'" class="achievements">
    <section-title> Achievements </section-title>
    <ul class="achievements__list list-reset">
      <li class="achievements__item" v-for="item in achievements" :key="item.id">
        <AchievementsCard :achievement="item" />
      </li>
    </ul>
  </section>
</template>

<script>
import achievementsData from '@/db/achievements';
import SectionTitle from '@/components/UI/SectionTitle.vue';
import AchievementsCard from '@/components/AchievementsCard.vue';
export default {
  components: { SectionTitle, AchievementsCard },
  data() {
    return {
      achievements: achievementsData
    }
  }
};
</script>

<style lang="scss" scoped>
.achievements {

  &__list {
    position: relative;
    display: flex;
    flex-direction: column;
    gap: 22px;

    &::before {
      content: '';
      display: block;
      position: absolute;
      top: 0;
      bottom: 0;
      left: 12px;
      width: 1px;
      background-color: #f7f9fc;
    }
  }
}

</style>
