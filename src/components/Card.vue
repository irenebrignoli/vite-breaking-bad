<script>
export default {
  name: "Card",
  props: {
    images: String,
    sets: Array,
  },
};
</script>

<template>
  <div class="card">
    <img
      v-for="image in images"
      :src="image.image_url"
      class="card-img-top"
      alt="..."
    />
    <div v-for="set in sets" class="card-body">
      <h5 class="card-title">{{ set.set_name }}</h5>
      <div class="card-text rarity">
        {{ set.set_rarity }}
      </div>
      <div class="card-text price">
        {{ set.set_price }}
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
@use "../styles/partials/variables";
</style>
