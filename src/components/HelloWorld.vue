<template>
  <div id="exercise">
    <!-- 1) Show an alert when the Button gets clicked -->
    <div>
        <button v-on:click="alertMe">Show Alert</button>
    </div>
    <!-- 2) Listen to the "keydown" event and store the value in a data property (hint: event.target.value gives you the value) -->
    <div>
        <input type="text" v-on:keydown="value = $event.target.value">
        <p>{‌{ value }}</p>
    </div>
    <!-- 3) Adjust the example from 2) to only fire if the "key down" is the ENTER key -->
    <div>
        <input type="text" v-on:keydown.enter="value = $event.target.value">
        <p>{‌{ value }}</p>
    </div>
</div>
</template>

<script>
export default {
  name: "HelloWorld",
  data: function() {
    return {
      value: String
    };
  },
  created: function() {
    value = "";
  },
  props: {
    msg: String
  },
  methods: {
    
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
