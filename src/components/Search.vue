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
  <div class="selector mb-3">
    <label for="select">Select Archetype</label>
    <select
      id="select"
      @change="$emit('selectArchetype')"
      v-model="store.value"
    >
      <option
        v-for="(archetype, i) in archetypeArray"
        :key="i"
        :value="archetype.archetype_name"
      >
        {{ archetype.archetype_name }}
      </option>
    </select>
  </div>
</template>

<style lang="scss" scoped>
@use "../styles/partials/variables";

.selector {
  label {
    font-weight: 600;
    color: #333;
    margin-right: 20px;
  }
  select {
    border-radius: 3px;
  }
}
</style>
