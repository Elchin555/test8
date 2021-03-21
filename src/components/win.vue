<template>
<div class="container">
  <p>Congratulations , You win! </p>
 <button @click="newGame">New Game</button>
</div>
</template>


<script>
export default {
  methods:{
    newGame(){
      this.$emit("data","gameCards")
    }
  }
}
</script>

<style scoped>
.container{
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
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
  background-color: rgb(14, 255, 142);
  transition: .5s;
}
.container p{
  color:rgb(111, 255, 15);
  font-size: 250%;
}

</style>