<template>
  <div class="hello">
    <h1>{{msg}}</h1>
    <p v-show='message'>terms and conditions</p>
    <button v-on:click="message=  !message">Please click to hide</button>
  
  </div>
</template>

<script>
  export default {
    name: 'HelloWorld',
    props: {
      msg: String
    },
    data: function() {
      return {
        message: true,
      }
    },
    methods: {
      output: function(v) {
        alert(v)
      }
    }
  }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss" scoped>
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
  .hello{
    background-image: url('~@/assets/img/building.jpg');
    height: 900px;
    width: 100vw;
    background-size: cover;
  }
</style>
