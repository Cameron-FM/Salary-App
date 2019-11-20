<template>
    <div id="navBar">
      <div id="logo">
        Salary Chart
      </div>
      <div id="nextBtn" v-on:click="switchPage">
        <a v-if="currentPage === 'landingPage'" :href="nextPageLink">Next</a>
      </div>
    </div>
</template>

<script>
export default {
  name: 'navBar',
  props: ['currentPage', 'nextPageLink'],

  methods: {
    switchPage: function() {
      this.$emit("nextBtnClicked", true)
    }
  }
}
</script>
  
<style>
  #navBar{
    background-color: #35495e;
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

  #nextBtn{
    float: right;
    margin-top: 5px;
    margin-right: 10px;
    width: 80px;
    height: 40px;
    background: #ff7e67;
    display: flex;
    justify-content: center;
  }

  #nextBtn a{
    font-family: 'Oxygen', sans-serif;
    color: #35495e;
    text-decoration: none;
    text-align: center;
    font-weight: bold;
    margin-top: 8px;
    font-size: 18px;
    display: inline-block;
    width:100%;
    height:100%;
  }
</style>
