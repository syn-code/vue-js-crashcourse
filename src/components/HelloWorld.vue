<template>
  <div class="hello">
    <h1>Hello World</h1>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  //props are specific to the component, which are encapsulated to that component
  // they are passed into the template with {{msg}}
  props: {
    msg: String
  }
}
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
