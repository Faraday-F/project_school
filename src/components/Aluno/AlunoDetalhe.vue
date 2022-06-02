<template>
  <div>
      <titulo :texto="`Aluno: ${aluno.nome}`" />
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
            aluno: {},
            idAluno: this.$route.params.id
        }
    },
    created() {
        this.$http
        .get("http://localhost:3000/alunos/" + this.idAluno)
        .then(res => res.json())
        .then(aluno => (this.aluno = aluno));

    },

    methods: {

    }


};
</script>

<
Titulostyle lang="scss" scoped></style>
