<template>

  <div>
    <h1>Vue JS Calculator APP</h1>
    <div class="calc-inner">
      <input type="text" v-on:keyup.enter="calcResult" placeholder="0" v-model="calcValue">

        <div class="btns">
          <button @click="enterValue(num)" v-for="num in numbs" :key="num">{{num}}</button>
          <button @click="enterValue(btn)" v-for="btn in btns" :key="btn">{{btn}}</button>
          <button @click="resetValue">R</button>
          <button @click="calcResult">=</button>
        </div>



    </div>


    {{message}}
  </div>
</template>

<script>
export default {
  name: "Calculator",
  data: function (){
    return {
      calcValue: ''
    }
  },
  props: {
    numbs: {
      type: Array,
      required: true
    },
    btns: {
      type: Array,
      required: true
    }
  },
  methods: {
    enterValue: function (num){
      this.calcValue = this.calcValue.toString()
        this.calcValue += num
    },
    resetValue: function (){

      this.calcValue = '';
    },
    calcResult: function (){

      this.calcValue = eval(this.calcValue)
    }
  }
}
</script>

<style scoped>

  .calc-inner{
    padding: 20px;
    max-width: 360px;
    width: 100%;
    margin: 0 auto;
  }

  .calc-inner input{
    width: 100%;
    padding: 20px 20px;
    width: 85%;
    border-radius: 5px;
    border: 2px tomato solid;

  }
  .btns{
    display: flex;
    justify-content: space-between;
    flex-wrap: wrap;
  }
  .calc-inner{
    border: 2px tomato solid;
    border-radius: 10px;
    background: rgba(0,0,0,0.7);
  }
  .calc-inner button, .calc-inner input{
    font-size: 20px;
  }
  .calc-inner button{
    width: 30%;
    padding: 15px 5px;
    margin: 5px;
    color: #fff;
    background: rgba(0,0,0,0.9);
    border-radius: 5px;
    border: 2px tomato solid;
    transition: 0.4s all ease;
  }
  .calc-inner button:hover{

    background: rgba(0,0,0,0.6);

  }
  .calc-inner button:last-child{
    width: 100%;
  }
</style>
