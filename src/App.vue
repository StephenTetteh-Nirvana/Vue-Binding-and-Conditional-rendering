<template>
  <!-- Basically binding attributes in arrays or objects -->
<div>{{ name }}</div>
<div v-html="greet"></div>
<div v-html="selector"></div>
<button v-bind:disabled="isDisabled">ON</button>
<h2 v-bind:class="isnew ? 'new' :'old'">movie tickets</h2>
<h2 v-bind:class="isnew && 'new'">same line</h2>
<h2 v-bind:class="[isold && 'text', isold ? 'isold' :'new']">Idea</h2>
<h2 v-bind:style="{
    color:'highlight',
    fontSize:'text',
}">Inline Style</h2>
<h2 v-bind:style="[list]">Big one</h2>
 
<!-- Conditional rendering -->
<h2 v-if="num === 0">The number is zero</h2>
<h2 v-else>The  number is not zero</h2>

<h2 v-for="name in names" :key="name.first">{{  name.first }} {{ name.last }}</h2>

<div v-for="actor in actors" :key="actor.name">
<h1>{{ actor.name }}</h1>
<h2 v-for="hobby in actor.hobbies" :key="hobby">{{ hobby }}</h2>
</div>
</template>

<script>

export default {
  name: 'App',
  data(){
    return{
        num:0,
        names:[
          {first:'Stephen',last:'Tetteh'},
          {first:'Micheal',last:'Ntumi'},
          {first:'Kwaku',last:'Amiwere'},
        ],
        actors:[
          {
            name:'Stephen Arthur',
            hobbies:['The Conjurer','Crucifix']
          },
          {
            name:'Maggie Essiam',
            hobbies:['Watching porno','Doing bad bitch things']
          },
          {
            name:'Micheal Ntumi',
            hobbies:['Movies','mommys boy']
          }
        ],
      // binding properties
      greet:'Goodmorning',
      isDisabled:false,
      isnew:true,
      isold:true,
      hightlight:'green',
      text:'50',
      list:{
            color:'green',
            fontSize:'50px',
            border:'1px solid green',
            padding:'20px,'
      }
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
.old{
  color:red;
}
.new{
  color:green;
}
.text{
  font-style:italic;
  text-decoration:underline;
}
</style>
