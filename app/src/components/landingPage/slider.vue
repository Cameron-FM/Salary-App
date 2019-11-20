<template>
    <div class="slidecontainer" >
        <span><input v-model.number="value" type="range" min="0" max="100" step="50" class="slider" id="sliderContainer"> </span>
        <p>{{value}} </p>
    </div>
</template>

<script>
export default {
  name: 'slider',

    data: () => {
        return{
          value: 50,
          itemValues: []
        }
    },

    watch: {
        value: function () {
            let items = document.querySelectorAll(".slider")
            for(let i=0; i < items.length; i++){
                this.itemValues[i] = items[i].value
            }
            this.$emit("updateItemValues", this.itemValues)
        }
    }
}
</script>
  
<style>
    .slidecontainer {
    width: 100%;
    margin-top: 25px;
    display: inline-block;
    }

    .slider {
    -webkit-appearance: none;
    width: 100%;
    height: 15px;
    border-radius: 5px;
    background: #d3d3d3;
    outline: none;
    opacity: 0.7;
    -webkit-transition: .2s;
    transition: opacity .2s;
    }

    .slider:hover {
    opacity: 1;
    }

    .slider::-webkit-slider-thumb {
    -webkit-appearance: none;
    appearance: none;
    width: 25px;
    height: 25px;
    border-radius: 50%;
    background: #ff7e67;
    cursor: pointer;
    }


</style>