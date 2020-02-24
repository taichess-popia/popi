<template functional>
  <div class="flex-start pull-start">
    <span class="create-margin-offset"
      ><img src="~/assets/images/icons/circleCheckmark.svg"
    /></span>
    <p>{{ props.feature }}</p>
  </div>
</template>

<style lang="scss" scoped>
@import "../assets/css/partials/_variables.scss";
@import "../assets/css/partials/_mixins.scss";

.create-margin-offset {
  margin-right: 0.5rem;
  @include breakpoint($xLarge) {
    margin-left: calc(-20px - 0.5rem);
  }
}
</style>
