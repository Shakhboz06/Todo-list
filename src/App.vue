<template>
  <div id="app">
    <Header />
    <Products />

    {{ a }}

    <div
      @click="ToggleClass()"
      :class="{ active: isActive }"
      class="example"
    ></div>

    <hr />

    <!-- Вызываем фукнции в событиях -->
    <button @mousemove="CountMinus(false)">Click -!</button>
    <button @mousemove="CountMinus(true)">Click +!</button>
    <button @mousemove="CountMinus(false)">Click -!</button>
    <button @mousemove="CountMinus(true)">Click +!</button>
    <button @mousemove="CountMinus(false)">Click -!</button>
    <button @mousemove="CountMinus(true)">Click +!</button>
    <button @mousemove="CountMinus(false)">Click -!</button>
    <button @mousemove="CountMinus(true)">Click +!</button>
    <button @mousemove="CountMinus(false)">Click -!</button>
    <button @mousemove="CountMinus(true)">Click +!</button>
  </div>
</template>

<script>
import Header from "./components/Header.vue";
import Products from "./components/Products.vue";

export default {
  name: "App",
  data: () => {
    return {
      a: 1,
      isActive: true,
    };
  },
  methods: {
    ToggleClass: function () {
      this.isActive = !this.isActive;
    },
    CountMinus: function (toTop) {
      // Тернарный оператор - вместо if else
      toTop ? this.a++ : this.a--;

      //   if(toTop == true) this.a++
      //   else this.a--
    },
  },
  components: {
    Header,
    Products,
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
.example {
  transition: 0.3s ease;
  width: 300px;
  height: 300px;
  background-color: #f0f0f0;
  margin: 0 auto;
}
.active {
  background: red;
  transform: rotate(45deg);
}
</style>
