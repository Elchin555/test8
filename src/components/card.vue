<template>
  <div class="card">
        <img :src="card.image" alt="" />
      </div>
</template>

<script>
export default {
      props:["card"],

  data() {
    return{
    }
    
  },
}
</script>

<style scoped>
.card{
  width: 10%;
  height: 10%;
  border-radius: 5px;
  border:1px solid black;
  transition:box-shadow .5s;
  margin-left: 15px;
  margin-top: 15px;

}
.card:hover{
  box-shadow: 0px 5px 48px grey;
  transition:box-shadow .5s;
}
.card img{
  width: 100%;
  height: 100%;
}
</style>