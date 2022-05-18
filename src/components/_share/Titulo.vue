<template>
    <div>
        <h1>{{texto}}</h1>
    </div>
</template>

<script>
    export default {
        props:{
            texto: String
        }
        
    }
</script>

<style scoped>

h1 {
    border: 1px solid black;
    text-align: center;
    text-shadow: 10px solid black;
}
    

</style>