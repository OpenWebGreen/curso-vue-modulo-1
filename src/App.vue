<template>
  <div>
    <form @submit.prevent="submeterForm">
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
export default {
  data() {
    return {
      pessoa: { endereco: {} }
    }
  },
  methods: {
    submeterForm() {
      console.info(this.pessoa)

      this.pessoa = { endereco: {} }
    }
  }
}
</script>

