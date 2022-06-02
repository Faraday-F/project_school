<template>
  <div>
    <Titulo
      :texto="
        professorid !== undefined
          ? 'Professor: ' + professor.nome
          : 'Todos os alunos'
      "
    />
    <div v-if="professorid !== undefined">
      <input
        class="input"
        type="text"
        placeholder="Nome do aluno"
        v-model="nome"
        v-on:keyup.enter="addaluno()"
      />

      <!--input class="input2" type="text" placeholder="Sobrenome" v-model="sobrenome"
    v-on:keyup.enter="addaluno"-->

      <button class="btn_add" @click="addaluno">Adicionar</button>
    </div>

    <table>
      <thead>
        <th>ID</th>
        <th>Nome</th>
        <!--th>sobrenome</!--th-->
        <th class="opt">Opçoes</th>
      </thead>
      <tbody v-if="alunos.length">
        <tr v-for="(aluno, index) in alunos" :key="index">
          <td>{{ aluno.id }}</td>
          <router-link :to="`/alunodetalhe/${aluno.id}`" tag="td" style="cursor:pointer">
            {{aluno.nome}} {{aluno.sobrenome}}
          </router-link>
            
            
          <!--th>{{aluno.sobrenome}}</!--th-->


          <td>
            <button class="btn" @click="remover(aluno)">Remover</button>
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
import Titulo from "../_share/Titulo.vue";
export default {
  components: {
    Titulo,
  },

  data() {
    return {
      titulo: "Alunos",
      professorid: this.$route.params.prof_id,
      professor: {},
      nome: "",
      sobrenome: "",
      alunos: [],
    };
  },
  created() {
    this.carregarProfessores();
    if (this.professorid) {
      this.$http
        .get("http://localhost:3000/alunos?professor.id=" + this.professorid)
        .then((res) => res.json())
        .then((alunos) => (this.alunos = alunos));
    } else {
      this.$http
        .get("http://localhost:3000/alunos")
        .then((res) => res.json())
        .then((alunos) => (this.alunos = alunos));
    }
  },

  props: {},
  methods: {
    addaluno() {
      let _aluno = {
        nome: this.nome,
        sobrenome: "",
        professor: {
          id: this.professor.id,
          nome: this.professor.nome
        }
      };

      this.$http
        .post("http://localhost:3000/alunos", _aluno)
        .then((res) => res.json())
        .then((alunoRetornado) => {
          this.alunos.push(aluno);
          this.nome = "";
          this.sobrenome = "";
        });
    },

    remover(aluno) {
      this.$http.delete(`http://localhost:3000/alunos/${aluno.id}`).then(() => {
        let indice = this.alunos.indexOf(aluno);
        this.alunos.splice(indice, 1);
      });
    },
    carregarProfessores() {
      this.$http
        .get("http://localhost:3000/Professores/" + this.professorid)
        .then((res) => res.json())
        .then((Professor) => {
          this.professor = Professor;
        });
    },
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.celula {
  margin-left: 500px;
}
</style>
