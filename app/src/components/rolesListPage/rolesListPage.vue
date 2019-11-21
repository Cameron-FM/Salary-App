<template>
  <div>
    <div id="container">
        <div class="card" v-for="role in roles">
            <div class="title"><h2>{{role.name}}</h2></div>
            <div class="salary"><p>{{role.salary}}</p></div>
            <div class="btnContainer">
            <div class="readMoreBtn"><a :href="role.link">Read More</a></div>
            </div>
        </div>
    </div>
  </div>
</template>

<script>
import json from '@/components/rolesListPage/roles.json'

  export default {
    name: 'rolesListPage',
    data: function() {
        return{
            roles: json
        }
    }


  }
</script>

<style>
    #container {
        display: grid;
        margin-top: 50px;
        grid-template-columns: repeat(auto-fit, 300px);
        grid-gap: 5%;
        grid-row-gap: 100px;
        justify-content: center;
    }

    .card{
        width: 300px;
        height: 200px;
        background-color: white;
        display: flex;
        justify-content: center;
        flex-direction: column;
        border-bottom: solid #35495e 7px; 
    }

    .title h2{
        text-align: center;
        font-family: 'Oxygen', sans-serif;
        color: #35495e;
    }

    .salary p {
        padding-top: 10px;
        text-align: center;
        color: #42b883; 
        font-size: 48px;
        font-family: 'Oxygen', sans-serif;
    }

    .btnContainer {
        margin-top: 20px;
        width: 100%;
    }

    .readMoreBtn:hover{
         background-color: #ff7e67; 
         cursor: pointer;
    }

    .readMoreBtn{
        float: right;
        margin-right: 25px;
        width: 100px;
        height: 40px;
        background-color: #35495e; 
        border-radius: 5px;
        border: none;
        outline: none;
        transition: ease 0.5s;
    }

    .readMoreBtn a{
        color: white;
        font-family: 'Oxygen', sans-serif;
        text-decoration: none;
        text-align: center;
        margin-top: 10px;
        font-size: 15px;
        display: inline-block;
        width:100%;
        height:100%;
        font-weight: 900;
    }

</style>