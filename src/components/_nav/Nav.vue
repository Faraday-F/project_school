<template>
    <div class="barraTop">
        <nav>
            <router-link to="/professores">Professores</router-link>
            <router-link to="/todosalunos">Alunos</router-link>
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
    margin-left: calc(50% - 165px);
    margin-right: calc(50% - 165px);
    
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

nav .router-link-exact-active {
    background-color: black;
    color: white;
    border-bottom: 4px solid;
    border-bottom-color: rgb(0, 0, 255);


}
</style>