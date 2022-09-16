<template>
  <section>
    <h1>Título</h1>

    <h2>Lista de Alunos:</h2>
    <p v-for="(aluno, index) in listaAlunos" :key="index">Aluno nº {{index}} - {{aluno}}</p>

    <h2>Lista de notas:</h2>
    <div v-if="exibirNotas === true">
      <p v-for="(nota, index) in listaNotas" :key="index">Nota nº {{index}} - {{nota}}</p>
    </div>
    <div v-else>
      <p>Exibição de nota não permitida.</p>
    </div>

    <h2>Importação de componente:</h2>
    <Alunos :lista="listaAlunos" />

    <h2>Input:</h2>
    <input type="text" v-model="aluno" />
    <button @click="addAluno(aluno)">Adicionar aluno</button>

    <p>Primeiro da turma: {{priemiroDaTurma}}</p>
  </section>
</template>

<script>
import Alunos from '../components/alunos.vue'

export default {
  name: 'IndexPage',
  head() {
    return {
      title: "HOME"
    }
  },
  data() {
    return {
      aluno: "",
      listaAlunos: ["Luís", "Lucas", "Wesley"],
      listaNotas: [5, 9, 2],
      exibirNotas: false
    }
  },
  methods: {
    addAluno(aluno) {
      this.listaAlunos.push(aluno),
        this.aluno = ""
    },
  },
  computed: {
    priemiroDaTurma() {
      // Lógica
      return this.listaAlunos[0]
    }
  },
  // Escutar alterações
  watch: {
    listaAlunos(novoValor, velhoValor) {
      alert("Lista foi alterada")
    }
  }
}
</script>

<style>

</style>
