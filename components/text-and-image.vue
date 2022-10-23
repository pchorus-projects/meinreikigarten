<template>
  <div class="root" :class="{ 'root--alternate': isAlternate }">
    <div class="description" :class="{ 'description--alternate': isAlternate }">
      <h2 class="heading heading--xl heading--xl-paragraph">{{ data.header }}</h2>
      <p v-for="text in data.text" :key="text" class="u-font-m u-font-m--paragraph">{{ text }}</p>
      <NuxtLink
        v-if="data.link"
        :to="data.link.path"
        :aria-label="data.link.text"
        class="button button--primary u-margin-top-m"
        >{{ data.link.text }}</NuxtLink
      >
    </div>
    <img v-if="data.image" class="image" :src="data.image.path" :alt="data.image.altText" />
  </div>
</template>

<script>
export default {
  props: {
    data: {
      type: Object,
      required: true,
    },
    isAlternate: {
      type: Boolean,
      required: true,
    },
  },
};
</script>

<style lang="scss" scoped>
@use '/assets/styles/variables';

.root {
  display: flex;
  align-items: center;

  &--alternate {
    flex-direction: row-reverse;
  }
}

.image {
  width: 420px;
  border-radius: variables.$border-radius-image;
}

.description {
  margin-right: variables.$space-xxl;
  flex: 1;

  &--alternate {
    margin-right: 0;
    margin-left: variables.$space-xxl;
  }
}

@media (max-width: variables.$max-width-mobile) {
  .image {
    width: 100vw;
    border-radius: 0;
  }
}

@media (max-width: variables.$max-width-tablet) {
  .root {
    flex-direction: column;
  }

  .description {
    margin: 0 0 variables.$space-l 0;

    &--alternate {
      margin: 0 0 variables.$space-l 0;
    }
  }

  // IE11 does not handle flex-box in flex-box both with direction column correctly
  @media (-ms-high-contrast: active), (-ms-high-contrast: none) {
    .root {
      display: block;
    }
  }
}
</style>
