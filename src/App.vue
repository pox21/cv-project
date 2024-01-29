<template>
  <main class="main">
    <TheSidebar />
    <div class="main__sections">
      <TheEducation />
      <TheAchievements />
      <TheToolsSkills />
      <TheLatestProjects />
      <TheCertificatesAwards />
    </div>
  </main>
</template>
<script>
import TheSidebar from '@/components/TheSidebar.vue';
import TheEducation from '@/components/TheEducation.vue';
import TheAchievements from '@/components/TheAchievements.vue';
import TheToolsSkills from '@/components/TheToolsSkills.vue';
import TheLatestProjects from '@/components/TheLatestProjects.vue';
import TheCertificatesAwards from '@/components/TheCertificatesAwards.vue';

export default {
  components: {
    TheSidebar,
    TheEducation,
    TheAchievements,
    TheToolsSkills,
    TheLatestProjects,
    TheCertificatesAwards
  },
  data() {
    return {};
  }
};
</script>

<style lang="scss" scoped>
.main {
  display: flex;
  gap: 20px;

  &__sections {
    position: relative;
    padding: 64px 48px 64px 12px;
    overflow: hidden;

    &::before {
      content: '';
      display: block;
      position: absolute;
      width: 1px;
      top: 64px;
      left: 28px;
      bottom: 0;
      background-color: #e2e6ee;
    }

    & > * {
      position: relative;
      padding-left: 64px;
      padding-bottom: 48px;

      // &::before {
      //   content: '';
      //   display: block;
      //   position: absolute;
      //   width: 1px;
      //   top: 0;
      //   left: 16px;
      //   bottom: 0;
      //   background-color: #e2e6ee;
      // }
    }
  }
}
</style>
