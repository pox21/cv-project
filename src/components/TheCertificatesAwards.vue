<template>
  <section class="certificates-awards">
    <section-title> Certificates & Awards </section-title>
    <ul class="certificates-awards__list list-reset">
      <li class="certificates-awards__item" v-for="item in certificates" :key="item.id">
        <certificatesAwardsCard :data="item" />
      </li>
    </ul>
  </section>
</template>

<script>
import certificatesData from '@/db/certificates';
import certificatesAwardsCard from '@/components/certificatesAwardsCard.vue';
import SectionTitle from '@/components/UI/SectionTitle.vue';
export default {
  components: { SectionTitle, certificatesAwardsCard },
  data() {
    return {
      certificates: certificatesData
    }
  }
};
</script>

<style lang="scss" scoped>

.certificates-awards {

  &__list {
    display: grid;
    grid-template-columns: 1fr;
    gap: 8px;
    border-radius: 8px;
    overflow: hidden;
  }

  &__item {
    background-color: var(--sidebar-bg-color);
  }
}

.card {
  padding: 15px 24px;
  display: flex;
  gap: 12px;

  @media(max-width: 576px) {
    padding: 10px;
  }

  &__img-wrapper {
    width: 43px;
    height: 43px;
  }

  &__img {
    width: 100%;
    height: 100%;
    object-fit: contain;
  }

  &__text-wrapper {
    display: flex;
    flex-direction: column;
  }

  &__pre-title {
    margin-bottom: auto;
    color: var(--gray-default);
    font-size: 13.604px;
    font-weight: 400;
    line-height: 17.491px; /* 128.571% */
    letter-spacing: 0.136px;
  }

  &__title {
    margin: 0;
    font-size: 13px;
    font-weight: 400;
    line-height: 17.491px; /* 128.571% */
    letter-spacing: 0.136px;
  }
  
  &__year {
    margin-left: auto;
    color: var(--gray-dark);
    font-size: 11.661px;
    font-weight: 400;
    line-height: 15.548px; /* 133.333% */
    letter-spacing: 0.117px;
  }
}
</style>
