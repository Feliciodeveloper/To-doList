<template>
  <div id="app">
    <Todolist/>
  </div>
</template>

<script>
import Todolist from "@/components/Todolist.vue"
export default {
  name: 'App',
  components:{
    Todolist
  }
}
</script>

<style>
*{
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
body{
  font-family: Roboto;
  color: #FFFFFF;
  background: url("./assets/pattern.svg") repeat top;
}
</style>
