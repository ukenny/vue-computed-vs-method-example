<template>
  <div>
    <button v-on:click="increase(2, $event)">
      Click Me
    </button>
    <p>
      {{ counter }}
    </p>
    <p v-on:mousemove="updateCoordinates">({{ x }}, {{ y }})</p>
  </div>
</template>

<script>
export default {
  name: "HelloWorld",
  data: function() {
    return {
      counter: Number,
      x: Number,
      y: Number
    };
  },
  created: function() {
    this.counter = 0;
    this.x = 0;
    this.y = 0;
  },
  props: {
    msg: String
  },
  methods: {
    // eslint-disable-next-line
    increase: function(step, event) {
      this.counter += step;
    },
    updateCoordinates: function(event) {
      this.x = event.clientX;
      this.y = event.clientY;
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
