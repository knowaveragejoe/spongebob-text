<template>
  <div id="app">
    <h1>Spongebob Mocking Text Generator</h1>

    <input type="text" v-model="inputText" />
    <hr />
    <h3>{{ spongebobText }}</h3>
  </div>
</template>

<script>
export default {
  name: "SpongebobTextGenerator",
  computed: {
    spongebobText() {
      return this.inputText
        .split("")
        .map((char) => {
          return Math.random() * 100 >= 50
            ? char.toUpperCase()
            : char.toLowerCase();
        })
        .join("");
    },
  },
  data() {
    return {
      inputText: "",
    };
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

input {
  text-align: center;
  width: 25em;
  height: 5em;
  font-size: 16px;
}
</style>
