<template>
  <div>
    <p>Counter is: {{ counter }}</p>
    <p>Clicks is: {{ clicks }}</p>
  </div>
</template>

<script>
// import { mapGetters } from "vuex";
export default {
  computed: {
    counter() {
      return this.$store.getters.doubleCounter;
    },
    clicks() {
      return this.$store.getters.stringCounter;
    },
  },
};
</script>

<style>
</style>