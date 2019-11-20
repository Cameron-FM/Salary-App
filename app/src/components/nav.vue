<template>
    <div id="navBar">
      <div id="logo">
        Salary Chart
      </div>
      <button v-if="currentPage === 'landingPage'" v-on:click="switchPage" >Next</button>
    </div>
</template>

<script>
export default {
  name: 'navBar',
  props: ['currentPage'],

  methods: {
    switchPage: function() {
      console.log("yh")
      this.$emit("switchPage", 'infoPage')
    }
  }
}
</script>
  
<style>
  #navBar{
    background-color: #42b883;
    width: 100%;
    height: 50px; 
  }

  #logo{
    margin-left: 10px;
    margin-top: 6px;
    float: left;
    color: white;
    font-family: 'Oxygen', sans-serif;
    font-size: 26px;
    font-weight: bold;
    text-align: center;
  }

  button{
    float: right;
  }
</style>
