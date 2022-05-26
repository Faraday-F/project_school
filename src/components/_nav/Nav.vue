<template>
    <div class="barraTop">
        <nav>
            <router-link to="/Professores">Professores</router-link>
            <router-link to="/alunos">Alunos</router-link>
            <router-link to="/sobre">Sobre</router-link>
        </nav>
    </div>
</template>

<script>
    export default {
        
    }
</script>

<style scoped>
.barraTop {
    background-color: rgb(230,230,230);
}

nav {
    padding: 20px 20px 20px 0px;
    margin-left: calc(35% - 100px);
    
}

nav a {
    padding: 10px;
    text-decoration: none;
    background-color: white;
    border-radius: 3px;
    color: blue;
    font-weight: bold;
    margin-right: 15px;



}
</style>