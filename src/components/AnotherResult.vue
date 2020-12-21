<template>
  <div>
    <p>Counter is: {{ doubleCounter }}</p>
    <p>Clicks is: {{ stringCounter }}</p>
  </div>
</template>

<script>
import * as types from "../store/types";

import { mapGetters } from "vuex";
export default {
  computed: {
    // ...mapGetters(["doubleCounter", "stringCounter"]),
    ...mapGetters({
      doubleCounter: types.DOUBLE_COUNTER,
      stringCounter: types.CLICK_COUNTER,
    }),
  },
};
</script>

<style>
</style>