<template>
  <div class="hello">
    <h1>{{msg}}</h1>
    <img class="imgSRC" src="../assets/logo.png">
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  data(){
    return{
      msg:"ToDoList",
      message:'',
      imgseen:false,
      arr:[
        {subject:"vichea",id:1},{subject:"hello",id:2},{subject:"sdadada",id:3}
      ]
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
.imgSRC{
  margin-bottom: 40px;
  height: 75px;
  display: block;
  margin: 28px auto;
}
</style>
