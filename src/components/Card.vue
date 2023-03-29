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
  <div class="card">
    <img :src="images[0].image_url" class="card-img-top" :alt="images[0].id" />
    <div class="card-body ms_card_body">
      <h5 class="card-title">{{ name }}</h5>
      <div class="card-text rarity">
        {{ archetype }}
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
@use "../styles/partials/variables";
{
.ms_card_body{
  min-height: 200px;
}
</style>
