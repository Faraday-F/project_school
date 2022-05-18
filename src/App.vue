<template>
  <div id="app">   
    <Alunos/>
  </div>
</template>

<script>
import Alunos from './components/Aluno/Alunos.vue'

export default {
  name: 'App',
  components: {
    Alunos
  }
}
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Roboto:ital,wght@1,300&display=swap');
body{
  background-color: #eee;
  font-family: 'Roboto:ital', cursive;
  display: grid;
  justify-items: center;
}

body, html {
  margin: 0;
  height: 100%;
}

#app {
  
}

.btn{
  background-color: #ca3e3e;
  border: 1px solid black;
  padding: 10px 20px;
  cursor: pointer;
  color: white;
  font-weight: bold;
  border-radius: 5px;
  border-bottom: 3px solid black; 
}

.btn:hover{
  text-shadow: 1px 1px 1px black;
  margin-top: 3px;
  border-bottom: 1px solid black;

}

.btn_add{
  background-color: #42ca3e;
  border: 1px solid black;
  padding: 10px 20px;
  cursor: pointer;
  color: white;
  font-weight: bold;
  border-radius: 5px;
  border-bottom: 3px solid black; 
}

.btn_add:hover{
  text-shadow: 1px 1px 1px black;
  margin-top: 3px;
  border-bottom: 1px solid black;

}

.input{
  border: 2px solid black;
  padding: 10px 20px;
  border-radius: 5px;
}

table {
  margin: 0px;
  padding: 0px;
  list-style-type: none;
  width: 100%;
}

.header {
  border: 1px solid black;
  justify-items: center;
  background-color: #ffffff;
  
}

table tr td{
  padding: 20px;
  font-size: 1.3em;
  background-color: #e0edf4;
  margin-bottom: 2px;
  color: #3e5252;
}

table tr td:hover {
  padding: 20px;
  font-size: 1.3em;
  background-color: #6ec6f5;
  margin-bottom: 2px;
  color: #3e5252;

}

table thead th {
  background-color: rgb(89, 156, 243) !important;
  font-size: 1.2em;
  padding: 10px 0px;
  text-align: center !important;

}


.colPequeno {
  width: 5%;
}



</style>
