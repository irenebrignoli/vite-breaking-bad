<script>
import { store } from "../store";

export default {
  name: "Loading",
  data() {
    return {
      store,
    };
  },
};
</script>

<template>
  <div v-if="store.loading == true" class="loading">Page is loading...</div>
</template>

<style lang="scss" scoped>
.loading {
  font-size: 30px;
  color: #333;
  background-color: white;
  font-weight: 600;
  width: 100%;
  height: 100%;
  padding-top: 100px;
  text-align: center;
  position: absolute;
  top: 0;
  left: 0;
}
</style>
