<template>
  <div id="helloWorld">
    <!-- 1) Show an alert when the Button gets clicked -->
    <div>
      <button v-on:click="alertMe">Show Alert</button>
    </div>
    <!-- 2) Listen to the "keydown" event and store the value in a data property (hint: event.target.value gives you the value) -->
    <div>
      <input type="text" v-on:keydown="storeValue($event)" />
      <p>{{ value }}</p>
    </div>
    <!-- 3) Adjust the example from 2) to only fire if the "key down" is the ENTER key -->
    <div>
      <input type="text" v-on:keydown.enter="storeValueTwo($event)" />
      <p>{{ valueTwo }}</p>
    </div>
  </div>
</template>

<script>
export default {
  name: "HelloWorld",
  data: function() {
    return {
      value: String,
      valueTwo: String
    };
  },
  created: function() {
    this.value = "";
    this.valueTwo = "";
  },
  props: {
    msg: String
  },
  methods: {
    alertMe() {
      this.$dialog.alert("Alert Being Shown");
    },
    storeValue(event) {
      this.value = event.target.value;
    },
    storeValueTwo(event) {
      this.valueTwo = event.target.value;
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
