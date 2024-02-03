<template>
  <main class="main">
    <TheSidebar :is-open="isSidebarOpen" />
    <button class="sidebar-open" @click="toggleSidebar">
      <inline-svg src="img/icons/burger.svg" />
    </button>
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
    return {
      isSidebarOpen: true,
    };
  },
  methods: {
    toggleSidebar() {
      this.isSidebarOpen = !this.isSidebarOpen;
    }
  },
  watch: {
    isSidebarOpen: {
      immediate: false,
      handler(val) {
        console.log(val)
        document.body.classList.toggle('no-scroll', !val);
      }
    }
  }
};
</script>

<style lang="scss" scoped>

.sidebar-open {
  display: none;
  position: absolute;
  top: 10px;
  left: 10px;
  padding: 0;
  background-color: transparent;
  border: none;
  z-index: 5;
  cursor: pointer;
  svg {
    width: 34px;
    height: 34px;
    object-fit: cover;
  }

  @media(max-width: 1200px) {
    display: block;
  }
}
.main {
  display: flex;
  gap: 20px;

  &__sections {
    position: relative;
    padding: 64px 48px 64px 12px;
    overflow: hidden;

    @media(max-width: 1200px) {
      padding-right: 20px;
    }

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

      @media(max-width: 1200px) {
        padding-left: 40px;
      }

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
