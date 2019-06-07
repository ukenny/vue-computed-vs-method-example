<template>
  <div id="helloWorld">
    <button v-on:click="counter++">Increase</button>
    <button v-on:click="counter--">Decrease</button>
    <button v-on:click="secondCounter++">Increase Second Counter</button>
    <p>Counter: {{ counter }} | {{ secondCounter }}</p>
    <p>Result: {{ result() }} | {{ output }}</p>
  </div>
</template>

<script>
export default {
  name: "HelloWorld",
  data: function() {
    return {
      counter: Number,
      secondCounter: Number
    };
  },
  created: function() {
    this.counter = 0;
    this.secondCounter = 0;
  },
  props: {
    msg: String
  },
  computed: {
    output: function() {
      console.log("\n-----Computed-----");
      return this.counter > 5 ? "Greater than 5" : "Equal to or less than 5";
    }
  },
  methods: {
    result: function() {
      console.log("\n*****Method*****");
      return this.counter > 5 ? "Greater than 5" : "Equal to or less than 5";
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
