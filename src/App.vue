<template>
  <div id="app">
    <div class="row">
      <div class="col-xs-12 col-sm-8 col-sm-offset-2 col-md-6 col-md-offset-3">
        <h1>Vuex</h1>
        <Result></Result>
        <hr />
        <another-result></another-result>
        <hr />
        <Counter></Counter>
        <hr />
        <another-counter></another-counter>
        <br />
        <hr />
        <p>{{ value }}</p>
        <br />
        <input type="text" :value="value" @input="updateValue" />
        <hr />
        <input type="text" v-model="valuemodel" />
      </div>
    </div>
  </div>
</template>

<script>
import Counter from "./components/Counter.vue";
import AnotherCounter from "./components/AnotherCounter.vue";
import Result from "./components/Result.vue";
import AnotherResult from "./components/AnotherResult.vue";

export default {
  name: "App",
  data: () => ({}),
  computed: {
    value() {
      return this.$store.getters.value;
    },
    valuemodel: {
      get() {
        return this.$store.getters.value;
      },
      set(value) {
        this.$store.dispatch("updateValue", value);
      },
    },
  },
  methods: {
    updateValue(event) {
      this.$store.dispatch("updateValue", event.target.value);
    },
  },
  components: {
    Counter,
    Result,
    AnotherResult,
    AnotherCounter,
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
