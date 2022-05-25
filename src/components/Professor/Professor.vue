<template>
  <div>
    <Titulo texto="Professores" />
    <div>
      <input
        class="input"
        type="text"
        placeholder="Nome do aluno"
        v-model="nome"
        v-on:keyup.enter="addaluno()"/>

      <!--input class="input2" type="text" placeholder="Sobrenome" v-model="sobrenome"
    v-on:keyup.enter="addaluno"-->

      <button class="btn_add" @click="addaluno">Adicionar</button>
    </div>

    <table>
      <thead>
        <th>ID</th>
        <th>Nome</th>
        <!--th>sobrenome</!--th-->
        <th class="opt">Qte. Alunos</th>
      </thead>
      <tbody v-if="professores.length">
        <tr v-for="(professor, index) in professores" :key="index">
          <td>{{ professor.id }}</td>
          <td>{{ professor.nome }}</td>
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
            professores: [
                {id: 1, nome:'Vine'},
                {id: 2, nome:'Giovana'},
                {id: 3, nome:'Chika'}
            ]
        }
    }
};
</script>

<style scoped></style>
