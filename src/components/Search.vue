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
  methods: {
    doReset() {
      this.store.value = "";
      this.$emit("selectArchetype");
    },
  },
};
</script>

<template>
  <div class="selector mb-3">
    <label for="select">Select Archetype</label>
    <select
      id="select"
      class="rounded-1"
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
    <button @click="doReset" class="ms-3 rounded-1">Reset</button>
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
}
</style>
