<template>


  <transition-group mode="out-in">
  <component
  class="animate__animated animate__heartBeat"
  @data="activeComponenet=$event"
  :is="activeComponenet"
  key="mainComponent"
  >
  
  </component>
  
  </transition-group>
  
  
  </template>
  
  <script>
  import gameCards from "./components/gameCards";
  import GameCards from './components/gameCards.vue';
  import lost from "./components/lost";
  import win from "./components/win"
  export default {
    components:{
  gameCards,lost,win
     
    },
   data(){
     return{
      activeComponenet:gameCards,
     }
   }
  }
  </script>