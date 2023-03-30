<script>
import { store } from "../store";

export default {
  name: "Search",
  data() {
    return {
      store,
    };
  },
  props: {
    archetypeArray: Array,
  },
};
</script>

<template>
  <label for="select"></label>
  <select id="select" @change="$emit('selectArchetype')" v-model="store.value">
    <option v-for="(type, i) in archetypeArray" :key="i" :value="type">
      {{ type }}
    </option>
  </select>
</template>

<style lang="scss" scoped>
@use "../styles/partials/variables";
</style>
