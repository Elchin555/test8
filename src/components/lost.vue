<template>
<div class="container">
  <p>You Lost</p>
 <button @click="newGame">New Game</button>
</div>
</template>


<script>
export default {
  methods:{
    newGame(){
      this.$emit("data","gameCards");
    },
    
}
}
</script>

<style scoped>
.container{
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
  background-color: red;
  width: 100%;
  height: 100vh;
}
.container button{
  width: 150px;
  height: 50px;
  transition: .5s;
  outline: none;
  border-radius: 5px;
  box-shadow: 2px 2px 8px grey;

}
.container button:hover{
  background-color: grey;
  transition: .5s;
}
.container p{
  color:white;
  font-size: 250%;
}

</style>