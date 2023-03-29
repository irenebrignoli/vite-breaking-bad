<script>
import Card from "./Card.vue";
export default {
  name: "CardsList",
  components: {
    Card,
  },
};
</script>

<template>
  <div class="cards-container">
    <Card />
  </div>
</template>

<style lang="scss" scoped>
@use "../styles/partials/variables";

.cards-container {
  background-color: variables.$list-bg-color;
  border-radius: 10px;
  padding: 50px;
  display: flex;
  flex-wrap: wrap;
}
</style>
