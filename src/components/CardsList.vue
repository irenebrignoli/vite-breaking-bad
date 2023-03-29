<script>
import Card from "./Card.vue";
import { store } from "../store";

export default {
  name: "CardsList",
  components: {
    Card,
  },
  data() {
    return {
      store,
    };
  },
};
</script>

<template>
  <div class="cards-container">
    <div v-for="(cardType, i) in store.cardData" class="card-box" :key="i">
      <Card :images="cardType.card_images" :sets="cardType.card_sets" />
    </div>
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

  .card-box {
    width: 230px;
  }
}
</style>
