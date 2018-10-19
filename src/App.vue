<template>
  <div class="center-flex">
    <loading :in-loading='loading' />
    <form v-if='!loading' @submit.prevent="submeterForm">
      <div>
        <label>
          Nome:
          <input v-model='pessoa.nome' type="text">
        </label>
      </div>
      <div>
        <label>
          Idade:
          <input v-model='pessoa.idade' type="number">
        </label>
      </div>
      <div>
        <label>
          Rua:
          <input v-model='pessoa.endereco.rua' type="text">
        </label>
      </div>
      <div>
        Sexo:
        <label>
          Masculino:
          <input v-model='pessoa.sexo' type="radio" value="m">
        </label>
        <label>
          Feminino:
          <input v-model="pessoa.sexo" type="radio" value="f">
        </label>
      </div>
      <button type="submit">Submeter</button>
    </form>
  </div>
</template>

<script>
import Loading from './components/Loading'

export default {
  components: { Loading },
  data() {
    return {
      loading: false,
      pessoa: { endereco: {} }
    }
  },
  methods: {
    submeterForm() {
      console.info(this.pessoa)

      this.pessoa = { endereco: {} }
    }
  },
  created() {
    this.loading = true
    setTimeout(() => {
      this.loading = false
      this.pessoa = {
        nome: 'Web Green',
        idade: 2,
        endereco: { rua: 'Rua dos Bobos' },
        sexo: 'm'
      }
    }, 2000)
  }
}
</script>

<style scoped>
.center-flex {
  display: flex;
  align-items: center;
  justify-content: center;
  flex-direction: column;
  height: 90vh;
}
</style>
