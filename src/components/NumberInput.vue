<template>
  <div id="app">
    <p v-for="(number, index) in numbers" :key="index">
      <input type="number" v-model.number="numbers[index]" />
    </p>

    <button v-on:click="addInput">{{ sumNumbers }}</button>
  </div>
</template>

<script>
export default {
  name: "NumberInput",
  components: {},
  data() {
    return {
      numbers: [10, 20, 25, 25, 20],
    };
  },
  computed: {
    sumNumbers: function() {
      let sum = 0;
      this.numbers.forEach((number) => {
        sum += number;
      });
      return sum;
    },
  },

  methods: {
    addInput: function() {
      let newInput = Math.trunc(Math.random() * 10) + 1;
      this.numbers.push(newInput);
    },
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

button,
input {
  width: 300px;
}
</style>
