<script>
import Header from "./components/Header.vue";
import CardsList from "./components/CardsList.vue";

export default {
  components: {
    Header,
    CardsList,
  },
};
</script>

<template>
  <Header />
  <main class="pt-5">
    <div class="container">
      <CardsList />
    </div>
  </main>
</template>

<style lang="scss">
@use "./styles/general.scss";
</style>
