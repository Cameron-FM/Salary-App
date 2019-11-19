<template>
  <div id="app">

    <template v-if = "currentPage === 'landingPage'">
      <landingPage @switchPage="openPageComponent" :currentPage="currentPage"/>
    </template>

  </div>
</template>

<script>
  import landingPage from './components/landingPage/landingPage.vue'

  export default {
    name: 'app',
    components: {
      landingPage
    },

    data: () => {
      return{
        currentPage: "landingPage"
      }
    },

    methods: {
      openPageComponent: function(page){
        this.currentPage = page
      }
    }
    
  }

</script>

<style>

</style>
