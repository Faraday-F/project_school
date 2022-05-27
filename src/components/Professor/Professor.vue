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
      <tbody v-if="professores.length">
        <tr  v-for="(professor, index) in professores" :key="index">
          <td>{{ professor.id }}</td>
           <router-link to="/alunos" tag="td" style="cursor: pointer">{{ professor.nome }}</router-link> 
          <!--th>{{professor.sobrenome}}</!--th-->
          <td>
            3
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
import Titulo from '../_share/Titulo.vue';

export default {
    components: {
        Titulo
    },
    data() {
        return {
            professores: []
        };
    },
    created() {
    this.$http
    .get('http://localhost:3000/professores')
    .then(res => res.json())
    .then(Professor => (this.professores = Professor))
    

  },

  props: {}

};
</script>

<style scoped></style>
