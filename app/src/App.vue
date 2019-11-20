<template>
  <div id="app">
    <navBar @switchPage="openPageComponent" :currentPage="currentPage"/>

    <template v-if = "currentPage === 'landingPage'">
      <landingPage :currentPage="currentPage"/>
    </template>

  </div>
</template>

<script>
  import landingPage from './components/landingPage/landingPage.vue'
  import navBar from '@/components/nav.vue'

  export default {
    name: 'app',
    components: {
      landingPage, navBar
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
