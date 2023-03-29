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
    <div class="row justify-content-center flex-wrap">
      <div v-for="(card, i) in store.cardData" class="card-box my-3" :key="i">
        <Card
          :images="card.card_images"
          :name="card.name"
          :archetype="card.archetype"
        />
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
@use "../styles/partials/variables";

.cards-container {
  background-color: variables.$list-bg-color;
  border-radius: 10px;
  padding: 50px;

  .card-box {
    width: 240px;
  }
}
</style>
