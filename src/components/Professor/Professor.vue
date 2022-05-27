<template>
  <div>
    <Titulo texto="Professores" />

    <table>
      <thead>
        <th>ID</th>
        <th>Nome</th>
        <!--th>sobrenome</!--th-->
        <th class="opt">Qte. Alunos</th>
      </thead>
      <tbody v-if="Professores.length">
        <tr v-for="(professor, index) in Professores" :key="index">
          <td>{{ professor.id }}</td>
          <router-link to="/alunos" tag="td" style="cursor: pointer">{{
            professor.nome
          }}</router-link>
          <!--th>{{professor.sobrenome}}</!--th-->
          <td>
            {{ professor.qtdAlunos }}
          </td>
        </tr>
      </tbody>
      <tfoot v-else>
        Nenhum professor encontrado.
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
      Alunos: [],
      Professores: [],
    };
  },
  created() {
    this.$http
      .get("http://localhost:3000/alunos")
      .then((res) => res.json())
      .then((alunos) => {
        this.Alunos = alunos;
        this.carregarProfessores();
      });
  },

  props: {},
  methods: {
    pegarQtdAlunosPorProfessor() {
      this.Professores.forEach((professor, index) => {
        professor = {
          id: professor.id,
          nome: professor.nome,
          qtdAlunos: this.Alunos.filter(aluno => aluno.professor.id == professor.id).length,
        };
        this.Professores[index] = professor;
      });
    },
    carregarProfessores() {
      this.$http
        .get("http://localhost:3000/Professores")
        .then((res) => res.json())
        .then((Professor) => {
          this.Professores = Professor;
          this.pegarQtdAlunosPorProfessor();
        });
    }
  },
};
</script>

<style scoped></style>
