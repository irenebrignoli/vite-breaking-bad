<script>
import Header from "./components/Header.vue";
import CardsList from "./components/CardsList.vue";

import axios from "axios";
import { store } from "./store.js";

export default {
  components: {
    Header,
    CardsList,
  },
  data() {
    return {
      store,
    };
  },
  methods: {
    getCards() {
      axios
        .get("https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=0/")
        .then((response) => {
          console.log(response.data.data);
          this.store.cardData = response.data.data;
        });
    },
  },
  created() {
    this.getCards();
  },
};
</script>

<template>
  <Header />
  <main class="py-5">
    <div class="container">
      <CardsList />
    </div>
  </main>
</template>

<style lang="scss">
@use "./styles/general.scss";
</style>
