<template>
  <div id="app">  
    <Nav></Nav>
    <div class="marginPrincipal">
      <router-view :key="$route.fullPath"></router-view>
    </div>    
  </div>
</template>

<script>
import Alunos from './components/Aluno/Alunos.vue'
import Nav from './components/_nav/Nav.vue'
import Professor from './components/Professor/Professor.vue'
import Sobre from './components/Sobre/Sobre.vue'


export default {
  name: 'App',
  components: {
    Alunos,
    Professor,
    Sobre,
    Nav
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

.marginPrincipal{
  width: 50%;
  margin: auto;
}

#app {
  width: 100%;
}

.btn{
  background-color: #ca3e3e;
  border: 1px solid black;
  padding: 10px 20px;
  cursor: pointer;
  color: white;
  font-weight: bold;
  border-radius: 25px;
  border-bottom: 3px solid black;
  border-right: 3px solid black; 
  display: block;
  margin-left: auto;
  margin-right: auto;
}

.btn:hover{
  text-shadow: 1px 1px 1px black;
  margin-top: 3px;
  border-bottom: 1px solid black;
  border-right: 1px solid black;

}

.btn_add{
  border: none;
  width: 150px;
  background-color: #494949;
  padding: 10px 20px;
  cursor: pointer;
  color: white;
  font-weight: bold;
  border-radius: 3px; 
  
}

.btn_add:hover{
  text-shadow: 1px 1px 1px black;
  margin-top: 3px;
  border-bottom: 1px solid black;

}

.input{
  border: none;
  width: calc(100% - 190px);
  padding: 10px 20px;
  border-radius: 3px;
}

.input2{
  width: calc(80% - 195px);
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
  justify-items: center;
  background-color: #eee;
  
}

tr:hover td {
  background:rgb(158, 234, 255);
  color: wthite;
  }

table tr td{
  padding: 20px;
  font-size: 1.3em;
  background-color: #e0edf4;
  margin-bottom: 2px;
  color: #3e5252;
}



table thead th {
  background-color: rgb(129, 184, 255) !important;
  font-size: 1.2em;
  padding: 10px 0px;
  text-align: center !important;

}
.colPequeno {
  width: 5%;
}






</style>
