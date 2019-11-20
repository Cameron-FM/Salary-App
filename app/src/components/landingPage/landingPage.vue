<template>
  <div>
    <div id="contentContainer">
      <img id="profitsImg "src="@/assets/profits.png">

      <div id="questionSection">
        <h1>Firstly...</h1>
        <h2 style="margin-bottom: 70px;">Answer a few question to get you started</h2>
        <ol>
          <li v-for="question in questions"><span>{{question}}</span>
            <slider/>
          </li>
        </ol>
      </div>
    </div>
  </div>
</template>

<script>
  import slider from '@/components/landingPage/slider.vue'

  export default {
    name: 'landingPage', 
    props: ['currentPage'],
    components: {
      slider
    },

    data: () => {
      return {
        questions: []
      }
    },

    mounted () {
      this.$nextTick(() => {
        this.questions = ["Who is Suraj?", "Who is Cameron?", "What is Camraj Inc?"]
      })
    }
  }
</script>
  
<style>
  h1, h2, p, ol{
      font-family: 'Oxygen', sans-serif;;
      margin: 0;
      padding: 0;
    }

  ol{
    list-style: none;
    counter-reset: my-awesome-counter
  }

  li{
    font-family: 'Oxygen', sans-serif;
    margin-bottom: 75px;
    counter-increment: listNumCounter;
  }

  li::before{
    content: counter(listNumCounter) ". ";
    color: #42b883;
    font-weight: bold;
  }

  li span{
    padding-left: 5px;
  }

  #questionSection h1{
     color: #42b883;
      font-size: 62px;
  }

  #questionSection h2{
    color: #35495e;
    padding-top: 5px;
    font-size: 18px;
  }

  #contentContainer{
    width: 100%;
    margin-top: 50px;
    display: flex;
    justify-content: center;
  }

  #questionSection{
    margin-left: 150px;
  }
</style>
