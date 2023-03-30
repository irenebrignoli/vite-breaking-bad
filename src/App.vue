<script>
import Header from "./components/Header.vue";
import CardsList from "./components/CardsList.vue";
import Loading from "./components/Loading.vue";
import Search from "./components/Search.vue";

import axios from "axios";
import { store } from "./store.js";

export default {
  components: {
    Header,
    CardsList,
    Loading,
    Search,
  },
  data() {
    return {
      store,
    };
  },
  methods: {
    getCards() {
      let urlApi =
        "https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=0";

      if (store.value != "") {
        urlApi += `&archetype=${store.value}`;
      }

      axios.get(urlApi).then((response) => {
        this.store.cardData = response.data.data;
        this.store.loading = false;
      });
    },
    getArchetypeArray() {
      axios
        .get("https://db.ygoprodeck.com/api/v7/archetypes.php")
        .then((response) => {
          this.store.allArchetype = response.data;
        });
    },

    // getArchetypeArray() {
    //   this.store.cardData.forEach((card) => {
    //     if (
    //       !this.store.allArchetype.includes(card.archetype) &&
    //       !card.archetype == ""
    //     ) {
    //       this.store.allArchetype.push(card.archetype);
    //     }
    //   });
    // },
  },
  created() {
    this.getCards();
    this.getArchetypeArray();
  },
};
</script>

<template>
  <Header />
  <main class="py-5">
    <div class="container">
      <Search
        :archetypeArray="store.allArchetype"
        @selectArchetype="getCards"
      />
      <CardsList />
    </div>
  </main>
  <Loading />
</template>

<style lang="scss">
@use "./styles/general.scss";
</style>
