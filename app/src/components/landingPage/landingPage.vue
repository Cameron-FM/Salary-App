<template>
  <div>
    <div id="contentContainer">
      <div id="profitsImg">
        
      </div>

      <div id="questionSection">
        <h1>Firstly...</h1>
        <h2 style="margin-bottom: 50px;">Answer a few question to get you started</h2>
        <ol>
          <li v-for="question in questions"><span>{{question}}</span>
            <slider @updateItemValues="updateValues"/>
          </li>
        </ol>
      </div>
      <button id="allRoles" v-on:click="switchPage">All Tech Roles</button>
    </div>

  </div>
</template>

<script>
  import slider from '@/components/landingPage/slider.vue'

  export default {
    name: 'landingPage', 
    props: ['currentPage', 'nextBtnIsClicked'],
    components: {
      slider,
      itemValues: []
    },

    data: () => {
      return {
        questions: [],
        nextPageID: 1,
        itemValues: []
      }
    },

    mounted () {
      this.$nextTick(() => {
        this.questions = ["Would you rather deal with small details or the big picture? ", "What would your priority be, Quality or Time?", "Are you likely to plan for something in advance?"]
      })
    },

    methods: {
      updateValues: function(items){
          this.itemValues = items
        },
      
      switchPage: function(){
        this.$emit("allRolesClicked", "rolesListPage")
      }
    },

    watch: {
      nextBtnIsClicked: function(){
        let newLink = "https://stealth-mole.glitch.me/role/1"
        if(this.itemValues[0] === "50" && this.itemValues[1] === "50" && this.itemValues[2] === "100"){
          newLink = "https://stealth-mole.glitch.me/role/1"//Product Manager
        }else if(this.itemValues[0] === "50" && this.itemValues[1] === "50" && this.itemValues[2] === "50"){
          newLink = "https://stealth-mole.glitch.me/role/2"//UX
        }else if(this.itemValues[0] === "0" && this.itemValues[1] === "0" && this.itemValues[2] === "0"){
          newLink = "https://stealth-mole.glitch.me/role/3"//Software Engineer
        }else if(this.itemValues[0] === "100" && this.itemValues[1] === "100" && this.itemValues[2] === "100"){
          newLink = "https://stealth-mole.glitch.me/role/4"//Project Manager
        }else if(this.itemValues[0] === "50" && this.itemValues[1] === "50" && this.itemValues[2] === "0"){
          newLink = "https://stealth-mole.glitch.me/role/5"//Data Analyst
        }else if(this.itemValues[0] === "0" && this.itemValues[1] === "50" && this.itemValues[2] === "50"){
          newLink = "https://stealth-mole.glitch.me/role/6"//Solutions Architect
        }else if(this.itemValues[0] === "0" && this.itemValues[1] === "50" && this.itemValues[2] === "0"){
          newLink = "https://stealth-mole.glitch.me/role/7"//Technical Consultant
        }else if(this.itemValues[0] === "50" && this.itemValues[1] === "0" && this.itemValues[2] === "0"){
          newLink = "https://stealth-mole.glitch.me/role/8"//Systems Engineer
        }
        this.$emit("nextPageLink", newLink)
      }
    }
  }
</script>
  
<style>
  h1, h2, p, ol{
      font-family: 'Oxygen', sans-serif;
      margin: 0;
      padding: 0;
    }

  #profitsImg{
    width: 600px;
    height: 600px;
    background-image: url("../../assets/profits.png");
    background-repeat: no-repeat;
    grid-column-start: 1;
    grid-column-end: 2;
    grid-row-start: 1;
    grid-row-end: 1;
  }

  #allRoles{
    width: 250px;
    height: 50px;
    background-color: #42b883;
    transform: translateY(-90px);
    border-radius: 5px;
    font-family: 'Oxygen', sans-serif;
    color: white;
    font-size: 18px;
    outline: none;
    border: none;
    font-weight: 900;
    grid-column-start: 1;
    grid-column-end: 2;
    grid-row-start: 2;
    grid-row-end: 3;
    transition: ease 0.25s;
  }

  #allRoles:hover{
    cursor: pointer;
    color: #35495e;
  }

  ol{
    width: 450px;
    list-style: none;
    counter-reset: my-awesome-counter
  }

  li{
    font-family: 'Oxygen', sans-serif;
    margin-bottom: 75px;
    counter-increment: listNumCounter;
  }

   li:nth-last-child(1){
    margin-bottom: 0;
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
    display: grid;
    grid-template-columns: 1fr 1fr;
    grid-template-rows: 1fr 1fr;
    justify-items: center;
  }

  #questionSection{
    margin-left: 150px;
    grid-column-start: 2;
    grid-column-end: 3;
    grid-row-start: 1;
    grid-row-end: 1;
  }
</style>
