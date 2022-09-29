<script>
import { useCounterStore } from '../stores/counter';
import { mapStores,mapActions , mapState } from 'pinia';
export default {
  data() {
    return{
      nome_alteravel: "paulo",
    }
  },
  computed: {
    ...mapStores(useCounterStore),
    ...mapState(useCounterStore, ['count', "nome"]),

  },
  methods: {
    ...mapActions(useCounterStore, ["increment","altera_nome"])
  }
}
</script>
<template>
  <main>
    <h1>Casa :)</h1>
    <input type="text" v-model="novo_nome"/><button @click="altera_nome(novo_nome)">Salvar</button>
    <hr />
    {{ nome }}
    <hr /> 
    {{ count }} <button @click="increment">Aumentar</button>
  </main>
</template>
<style>
  h1{
    margin: 5px;
  }
  input{
    margin: 5px;
  }
</style>