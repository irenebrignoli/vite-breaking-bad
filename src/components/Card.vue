<script>
export default {
  name: "Card",
  props: {
    images: Array,
    name: String,
    archetype: String,
  },
};
</script>

<template>
  <div class="card ms_card rounded-2">
    <img :src="images[0].image_url" class="card-img-top" :alt="images[0].id" />
    <div class="card-body">
      <h5 class="card-title">{{ name }}</h5>
      <div class="card-text">
        {{ archetype }}
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
@use "../styles/partials/variables";

.ms_card {
  color: variables.$text-white-color;
  background-color: variables.$card-bg-color;

  .card-body {
    min-height: 100px;

    .card-title {
      font-size: 16px;
      font-weight: 600;
    }
  }
}
</style>
