<template functional>
  <div
    class="card half-stack"
    :class="props.strongShadow ? 'strong-shadow' : ''"
  >
    <h3 class="card__heading">{{ props.heading }}</h3>
    <div
      v-for="(listItem, index) in props.list"
      :key="`${index}-listItem`"
      class="flex-start pull-start"
    >
      <span class="mr-1"><img src="/images/icons/checkmark.svg"/></span>
      <p>{{ listItem }}</p>
    </div>
  </div>
</template>

<style lang="scss" scoped>
@import "../assets/css/partials/_variables.scss";

.card {
  background-color: $white;
  border-radius: 8px;
  padding: $card-padding $card-padding calc(#{$card-padding} * 2) $card-padding;
  border: 1px solid $grey;

  .card__heading {
    text-align: center;
    border-bottom: 1px solid lightgrey;
    padding-bottom: 1rem;
    min-height: 5rem;
  }
}

.mr-1 {
  margin-right: 1rem;
  display: inline-block;
}

.strong-shadow {
  box-shadow: 2px 2px 10px $lightgrey;
}
</style>
