<template>
    <div>
        <h3>Lista de alunos (Componente):</h3>
        <p v-for="aluno in lista">{{aluno}}</p>

    </div>
</template>

<script>
export default {
    name: "alunos",
    props: {
        lista: {
            type: Array,
            required: true
        }
    }
}
</script>