<template>
  <h2>{{ customTitle }}</h2>
  <p>{{ counter }} <sup>2</sup> = {{ getSquareValue }} </p>
  <button @click="increment">+1</button>
  <button @click="decrement">-1</button>
  
</template>

<script>
export default {

  props: {
    title: String,
    start: {
      type: Number,
      default: 100,
      // require: true
      validator( value ){
        return value > 100
      }
    }
  },
  
  data(){
    return{
      counter: this.start,
    }
  },
  methods: {
    
    increment(){
      this.counter++;
    },
    decrement(){
      this.counter--;
    }
  },
  computed: {
    getSquareValue(){
      return this.counter * this.counter;
    },
    customTitle(){
      return this.title ? this.title : 'Counter'; 
    }
  }

}
</script>

<style>

</style>