<template>
  <div>
    <hello></hello>
    <p>{{msg}}</p>
    <button @click="fnc">change</button>

  </div>
</template>

<script>
  import hello from "./components/HelloWorld"
export default {
  components:{
hello
  },
  data(){
    return{
      msg:"test"
    }
  },
  methods: {
    fnc(){
this.msg="auye jizn voram"
    }
  },
}
</script>