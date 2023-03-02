<template>
<h2>{{ name }}</h2>
<div>
<button v-on:click="nameChange(),increment(2)">Change name</button>
</div>
<h2>{{ count }}</h2>
<div>
  <button v-on:click="increment(2)">Increment by 2</button>
  <button v-on:click="decrement(2)">Decrement minus 2</button>
  <!-- <button v-on:click="count += 5">Increment by 5</button> -->
 <!-- <button v-on:click="count -= 5">Decrement minus 5</button> -->

 <button v-on:click="Color($event)">Click me</button>

</div>
</template>

<script>

export default {
  name: 'App',
  data(){
    return{
       count:0,
       name:'Stephen',
    }
  },
  methods:{
       nameChange(){
        this.name = 'Tetteh'
       },
      Color: function(event){
        event.target.style.backgroundColor ='yellow'
        console.log(event)
      },
      increment(num){
        this.count += num
      },
      decrement(num){
        this.count -= num
      }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
