<template>
  <div id="app">
    <navBar @nextBtnClicked="nextBtnClicked" :nextPageLink="nextPageLink" :currentPage="currentPage"/>

    <template v-if = "currentPage === 'landingPage'">
      <landingPage @nextPageLink="generateLink" :nextPageLink="nextPageLink" :currentPage="currentPage" :nextBtnIsClicked="nextBtnIsClicked"/>
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
        currentPage: "landingPage",
        nextBtnIsClicked: false,
        nextPageLink: ""
      }
    },

    methods: {
      openPageComponent: function(page){
        this.currentPage = page
      },

      nextBtnClicked: function(data){
        this.nextBtnIsClicked = true
      },

      generateLink: function(link){
        this.nextPageLink = link
      }
    }
    
  }

</script>

<style>

</style>
