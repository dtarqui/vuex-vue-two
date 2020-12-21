<template>
  <p>Counter is: {{ counter }}</p>
</template>

<script>
// export default {
//   computed: {
//     counter() {
//       //   return this.$store.state.counter * 2;
//       return this.$store.getters.doubleCounter;
//     },
//   },
// };
import * as types from "../store/types";

import { mapGetters } from "vuex";
export default {
  computed: {
    // ...mapGetters(["doubleCounter", "stringCounter"]),
    ...mapGetters({
      counter: types.DOUBLE_COUNTER,
    }),
  },
};
</script>

<style>
</style>