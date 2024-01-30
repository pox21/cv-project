<template>
  <section class="latest-project">
    <section-title> Latest projects </section-title>
    <ul class="latest-project__list list-reset">
      <li class="latest-project__item">
        <article class="card">
          <div class="card__wrapper">
            <div class="card__img-wrapper">
              <img :src="'img/latest-projects/figma.png'" alt="" class="card__img">
            </div>
            <div class="card__text-wrapper">
              <h3 class="card__title">Alexa Dev Community Landing Page</h3>
              <p class="card__descr">
                Web UI design for alexa developers comunity
              </p>
            </div>
          </div>
          <a href="#" target="_blank" class="card__link">
            <span class="card__link-icon">
              <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" viewBox="0 0 16 16" fill="none">
                <path d="M5.80907 13.4101C4.53458 13.4101 3.38558 12.6424 2.89777 11.4649C2.40996 10.2875 2.6794 8.93214 3.58047 8.0308L4.91788 6.69339L5.80907 7.58458L4.47229 8.92136C3.99459 9.39906 3.80802 10.0953 3.98287 10.7479C4.15772 11.4004 4.66742 11.9101 5.31997 12.085C5.97252 12.2598 6.66878 12.0733 7.14648 11.5956L8.48327 10.2588L9.37446 11.1506L8.03767 12.4874C7.44779 13.0802 6.64534 13.4124 5.80907 13.4101ZM6.25466 10.7044L5.36347 9.81318L9.82005 5.35661L10.7112 6.2478L6.25529 10.7037L6.25466 10.7044ZM11.1575 9.36759L10.2656 8.4764L11.6024 7.13961C12.0866 6.66335 12.2782 5.96397 12.1043 5.30743C11.9303 4.6509 11.4177 4.13809 10.7612 3.96401C10.1047 3.78993 9.40524 3.98133 8.92886 4.46542L7.59145 5.8022L6.70026 4.91101L8.03767 3.5736C9.26989 2.35213 11.2577 2.35648 12.4845 3.58334C13.7114 4.81019 13.7157 6.79796 12.4942 8.03017L11.1575 9.36696V9.36759Z" fill="#516CF7"/>
              </svg>
            </span>
            <span class="card__link-text">
              https//figma.com
            </span>
          </a>
        </article>
      </li>
      <li class="latest-project__item">
        <article class="card">
          <div class="card__wrapper">
            <div class="card__img-wrapper">
              <img :src="'img/latest-projects/Image.png'" alt="" class="card__img">
            </div>
            <div class="card__text-wrapper">
              <h3 class="card__title">Portfolio Webpage</h3>
              <p class="card__descr">
                Personal Portfolio webpage with resume and blog
              </p>
            </div>
          </div>
          <a href="#" target="_blank" class="card__link">
            <span class="card__link-icon">
              <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" viewBox="0 0 16 16" fill="none">
                <path d="M5.80907 13.4101C4.53458 13.4101 3.38558 12.6424 2.89777 11.4649C2.40996 10.2875 2.6794 8.93214 3.58047 8.0308L4.91788 6.69339L5.80907 7.58458L4.47229 8.92136C3.99459 9.39906 3.80802 10.0953 3.98287 10.7479C4.15772 11.4004 4.66742 11.9101 5.31997 12.085C5.97252 12.2598 6.66878 12.0733 7.14648 11.5956L8.48327 10.2588L9.37446 11.1506L8.03767 12.4874C7.44779 13.0802 6.64534 13.4124 5.80907 13.4101ZM6.25466 10.7044L5.36347 9.81318L9.82005 5.35661L10.7112 6.2478L6.25529 10.7037L6.25466 10.7044ZM11.1575 9.36759L10.2656 8.4764L11.6024 7.13961C12.0866 6.66335 12.2782 5.96397 12.1043 5.30743C11.9303 4.6509 11.4177 4.13809 10.7612 3.96401C10.1047 3.78993 9.40524 3.98133 8.92886 4.46542L7.59145 5.8022L6.70026 4.91101L8.03767 3.5736C9.26989 2.35213 11.2577 2.35648 12.4845 3.58334C13.7114 4.81019 13.7157 6.79796 12.4942 8.03017L11.1575 9.36696V9.36759Z" fill="#516CF7"/>
              </svg>
            </span>
            <span class="card__link-text">
              https://anuragyadav365.github.io
            </span>
          </a>
        </article>
      </li>
    </ul>
  </section>
</template>

<script>
import SectionTitle from '@/components/UI/SectionTitle.vue';
export default {
  components: { SectionTitle }
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

.card {
  display: flex;
  flex-direction: column;
  flex-grow: 1;
  max-width: 339px;
  padding: 24px;
  background-color: inherit;

  @media(max-width: 576px) {
    padding: 10px;
  }

  &__wrapper {
    display: flex;
    gap: 16px;
    margin-bottom: 2px;
  }

  &__img-wrapper {
    width: 48px;
    height: 48px;
  }

  &__img {
    width: 100%;
    height: 100%;
    object-fit: contain;
  }

  &__title {
    margin-top: 0;
    margin-bottom: 4px;
    color: var(--gray-darker);
    font-size: 16px;
    font-weight: 500;
    line-height: 20px; 
  }

  &__descr {
    margin: 0;
    color: var(--gray-default);
    font-size: 14px;
    font-weight: 400;
    line-height: 18px; 
    letter-spacing: 0.141px;
  }

  &__link {
    margin-top: auto;
    display: flex;
    align-items: center;
    gap: 12px;
  }

  &__link-icon {
    display: flex;
    align-items: center;
    justify-content: center;
    width: 24px;
    height: 24px;
    border-radius: 100%;
    background-color: #e1e7fe;
  }

  &__link-text {
    color: var(--Secondary-Default, #516CF7);
    font-family: 'Outfit';
    font-size: 16.135px;
    font-style: normal;
    font-weight: 600;
    line-height: 20.168px; /* 125% */
    text-decoration: underline;
    overflow-wrap: anywhere;
  }
}
</style>
