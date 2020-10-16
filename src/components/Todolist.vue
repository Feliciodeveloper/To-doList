<template>
  <div class="wrapper">
    <div class="title">
      <h1><span>To-Do</span>List</h1>
    </div>
    <div class="entries">
      <label for="item">Item:</label>
      <input type="text" name="item" id="item" v-model="value">
      <button @click.prevent="addList()">+ TO LIST</button>
    </div>
    <div class="list">
      <h2>list Do</h2>
      <ul v-if="list.length > 0">
        <li v-for="(item,index) in list" :key="index">
          <div>
            <p>{{item}}</p> 
            <button @click.prevent="removeList(index)">-</button>
          </div>
          <hr>
        </li>
      </ul>
    </div>
    <p class="dev">Desenvolvido por F. Neto</p>
  </div>
</template>

<script>
export default {
  name:"Todolist",
  data(){
    return {
      value: "",
      list: []
    }
  },
  methods:{
    addList(){
      if(this.value.length > 0){
        this.list.unshift(this.value);
        this.value = "";
      }else{
        window.alert("Digite algo para adicionar a lista");
      }
    },
    removeList(param){
      this.list.splice(param,1);
    }
  }
}
</script>

<style scoped>
  .wrapper{
    max-width: 775px;
    border-top-left-radius: 50px;
    background: #FF3D39;
    padding: 30px;
    margin: 36px auto;
    opacity: .95;
    position: relative;
    box-shadow: 0px 3px 4px rgba(0, 0, 0, 0.1), 0px 3px 10px rgba(0, 0, 0, 0.2);
  }
  .title{
    max-width: 380px;
    height: 76px;
    background: #D92E2C;
    display: flex;
    justify-content: center;
    align-items: center;
    margin: 0 auto 20px auto;
    font-weight: bold;
  }
  .title h1 {
    font-size: 2.25rem;
  }
  .title span {
    color: #00FFFE;
  }
  .entries{
    max-width: 600px;
    margin-left: 70px;
  }
  .entries label{
    font-size: 1.5rem;
    margin-right: 10px;
  }
  .entries input {
    background: none;
    border: 2px solid #FFFFFF;
    height: 40px;
    padding: 10px;
    width: 300px;
    margin-right: 20px;
    color: #FFFFFF;
    font-size: 1.125rem;
  }
  .entries input:focus, .entries button:focus{
    outline: none;
  }
  .entries button{
    border: none;
    background: #FFFFFF;
    color: #000000;
    height: 40px;
    width: 125px;
    font-weight: bolder;
    cursor: pointer;
  }
  .entries button:hover{
    background: #00FFFE;
    transform: scale(1.1);
  }
  .list {
    width: 380px;
    min-height: 430px;
    background: #FFFFFF;
    margin: 0 auto;
    border-bottom-right-radius: 40px;
    color: #000000;
    margin-top: 20px;
    padding-top: 15px;
    padding-bottom: 15px;
  }
  .list h2 {
    text-align: center;
    font-size: 1.125rem;
    margin-bottom: 30px;
  }
  .list ul{
    list-style: none;
  }
  .list li div {
    display: flex;
    justify-content: space-between;
    margin-bottom: 5px;
    margin: 0 30px;
  }
  hr{
    margin: 10px 15px;
  }
  .list button {
    width: 20px;
    height: 20px;
    border-radius: 10px;
    color: #FFFFFF;
    background: #FF3D39;
    border: none;
    cursor: pointer;
  }
  .dev{
    position: absolute;
    bottom: 0;
    right: 0;
    color: #00FFFE;
    margin: 15px;
    font-weight: bold;
  }
</style>