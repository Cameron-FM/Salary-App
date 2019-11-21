<template>
    <div id="navBar">
      <div id="logo"><a href="@components/landingPage/landingPage.vue">Seek Tech</a></div>
      <div v-if="currentPage === 'landingPage'" id="nextBtn" v-on:click="switchPage">
        <a :href="nextPageLink">Next</a>
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
    font-size: 26px;
    text-align: center;
  }

  #logo a{
    text-decoration: none;
    color: white;
    font-family: 'Oxygen', sans-serif;
    font-weight: bold;
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
    border-radius: 5px;
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
    transition: ease 0.25s;
  }

  #nextBtn a:hover{
    cursor: pointer;
    color: white;
  }
</style>
