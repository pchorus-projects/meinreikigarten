<template>
  <section class="hero">
    <img class="hero__image" src="~/assets/images/landing-page-hero.jpg" alt="Garten mit Bachlauf und Buddha" />
    <div class="hero__content">
      <!--      <Navigation></Navigation>-->
      <NuxtLink to="/#willkommen" class="hero__logo-container">
        <img
          class="hero__logo"
          src="~/assets/logos/mein-reikigarten.svg"
          alt="Mein Reikigarten Logo: Sabrina mit Lilien"
        />
      </NuxtLink>
      <p class="hero__gap"></p>
      <h1 class="hero__heading u-heading u-heading--white">Wer seinem Herz folgt,<br />kommt niemals vom Weg ab.</h1>
    </div>
  </section>
</template>

<style lang="scss" scoped>
@use 'assets/styles/variables';

.hero {
  position: relative;
  margin-bottom: 0;
  padding: 0;
  max-height: 768px;

  &__image {
    display: block; // remove gap at the image's bottom
    width: 100%;
    max-height: 768px;
    object-fit: cover;
  }

  &__content {
    position: absolute;
    top: 0;
    right: 0;
    bottom: 0;
    left: 0;
    padding: variables.$space-m variables.$space-xxxl;
    background-image: linear-gradient(rgba(0, 0, 0, 0) 50%, rgba(0, 0, 0, 0.4) 70%, rgba(0, 0, 0, 0.7) 100%);
    display: flex;
    flex-direction: column;
    align-items: flex-end;
    color: variables.$font-color-white;
  }

  &__gap {
    flex: 1;
  }

  &__logo-container {
    display: flex;
    align-items: center;
    justify-content: center;
    height: 460px;
    width: 460px;
    background: radial-gradient(
      circle,
      rgba(255, 255, 255, 0.6) 0%,
      rgba(255, 255, 255, 0.6) 25%,
      rgba(255, 255, 255, 0) 70%
    );
  }

  &__logo {
    width: 380px;
  }

  &__heading {
    font-family: variables.$font-family-header-default;
    font-size: 56px;
    text-align: center;
    margin-top: variables.$space-xl;
    margin-bottom: variables.$space-xxl;
  }
}

@media (max-width: variables.$max-width-desktop) {
  .hero {
    &__heading {
      margin-top: variables.$space-m;
      margin-bottom: variables.$space-m;
    }
  }
}

@media (max-width: variables.$max-width-tablet) {
  .hero {
    &__logo-container {
      width: 420px;
      height: 420px;
    }
    &__logo {
      width: 340px;
    }
    &__heading {
      font-size: variables.$font-size-xxl;
      margin-top: variables.$space-s;
      margin-bottom: variables.$space-xxs;
    }
  }
}

@media (max-width: variables.$max-width-mobile-landscape) {
  .hero {
    &__image {
      min-height: 600px;
    }
    &__content {
      align-items: center;
      padding: variables.$space-m variables.$space-m;
      background-image: linear-gradient(rgba(0, 0, 0, 0) 55%, rgba(0, 0, 0, 0.7) 100%);
    }
    &__logo-container {
      width: 380px;
      height: 380px;
    }
    &__logo {
      width: 300px;
    }
    &__heading {
      margin-top: variables.$space-m;
      margin-bottom: variables.$space-m;
    }
  }
}

@media (max-width: variables.$max-width-mobile) {
  .hero {
    &__heading {
      margin-top: variables.$space-xs;
      margin-bottom: variables.$space-xs;
    }
  }
}
</style>
