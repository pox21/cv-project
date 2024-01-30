<template>
  <aside class="sidebar" :class="{mobile: !isOpen}">
    <header class="sidebar__header">
      <div class="sidebar__avatar-wrapper">
        <img
          src="https://placehold.co/100x100"
          alt=""
          class="sidebar__avatar"
        />
      </div>
      <h1 class="sidebar__title">Anurag Yadav</h1>
      <p class="sidebar__subtitle">
        A well-organized, creative and goaloriented graduate possessing
        excellent communication, problem-solving and leadership skills with a
        flair to explore Computer Science Engineering
      </p>
    </header>
    <SidebarSection :contents="contacts" />
    <SidebarSection :contents="socials" title="Socials" />
    <SidebarSection :contents="language" title="Languages" />
    <SidebarSection :contents="hobbies" title="Hobbies & Interests" />
  </aside>
</template>

<script>
import SidebarSection from "@/components/SidebarSection.vue";
import contactsData from "@/db/contacts";
import socialsData from "@/db/socials";
import languagesData from "@/db/languages";
import hobbiesData from "@/db/hobbies";

export default {
  props: {
    isOpen: {
      type: Boolean,
      default: true
    }
  },
  data() {
    return {
      contacts: contactsData,
      socials: socialsData,
      language: languagesData,
      hobbies: hobbiesData,
    };
  },
  components: { SidebarSection },
};
</script>

<style lang="scss" scoped>
  .sidebar {
    position: relative;
    z-index: 1;
    flex-shrink: 0;
    max-width: 355px;
    padding: 48px;
    background-color: var(--sidebar-bg-color);

    @media(max-width: 1200px) {
      position: absolute;
      top: 0;
      left: 0;
      z-index: 5;
      transform: translateX(-100%);
      transition: transform .3s ease-in-out;
    }

    &.mobile {
      transform: translateX(0);
    }

    & > *:not(:nth-last-child(-n+2)) {
      border-bottom: 1px solid #e2e6ee;
    }

    & > *:last-child {
      padding-top: 0;
      gap: 16px;
    }

    &__header {
      font-family: Outfit;
    }

    &__avatar-wrapper {
      margin-bottom: 16px;
      width: 96px;
      height: 96px;
      border-radius: 100%;
      overflow: hidden;

      img {
        width: 100%;
        height: 100%;
        object-fit: cover;
      }
    }

    &__title {
      margin-top: 0;
      margin-bottom: 32px;
      color: var(--gray-darker);
      font-size: 32px;
      font-weight: 500;
      line-height: 40px;
      letter-spacing: -0.645px;
    }

    &__subtitle {
      margin: 0;
      padding-bottom: 10px;
      color: var(--gray-dark);
      
      font-size: 18px;
      font-weight: 500;
      line-height: 24px; /* 133.333% */
      letter-spacing: 0.363px;
    }

  }
</style>
