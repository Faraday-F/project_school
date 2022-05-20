<template>
  <div>
    <Titulo class="header" texto="Alunos.com"/>
    <div>

      <input class="input" type="text" placeholder="Nome do aluno" v-model="nome"
    v-on:keyup.enter="addaluno()"><button class="btn_add" @click="addaluno">
      ADD
    </button>

    </div>
    
    

    <table border="2px">
      <thead>
        <th>Matricula</th>
        <th>Nome</th>
        <th>Opçoes</th>
      </thead>
      <tbody v-if="alunos.length">
        <tr v-for="(aluno, index) in alunos" :key="index">
          <td>{{index+1}}</td>
          <!--td>{{aluno.id}}</!--td -->
          <td>{{aluno.nome}}</td>
          <td>
            <button class="btn" @click="remover(aluno)">Remover
            </button>
          </td>
        </tr>
      </tbody>
      <tfoot v-else>
        Nenhum aluno encontrado.
      </tfoot>
    </table>


  </div>
</template>

<script>
import TituloVue from '../_share/Titulo.vue';
import Titulo from '../_share/Titulo.vue';
export default {
  components: {
    Titulo,
    Titulo
},

  data() {
    return{
      titulo: 'Alunos.com.br',
      nome: '',
      alunos: []
    };
  },
  created() {
    this.$http
    .get('http://localhost:3000/alunos')
    .then(res => res.json())
    .then(alunos => this.alunos = alunos)

  },

  props: {},
  methods: {
    addaluno() {
        let _aluno = {
        nome: this.nome,
        sobrenome: ""
        }

        this.$http
    .post('http://localhost:3000/alunos', _aluno)
    .then(res => res.json())

        this.alunos.push(_aluno);
        this.nome = '';  
            
    },
        

    remover(aluno) {
      let indice = this.alunos.indexOf(aluno);
      this.alunos.splice(indice, 1)
      this.$http
    .delete(`http://localhost:3000/alunos${aluno.id}`)
    .then(
      
    )
      

    },
  },
  
  props: {
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
