<script>
import { mapStores,mapActions , mapState } from 'pinia';
import { useCounterStore } from '../stores/counter';
export default {
  computed: {
    ...mapStores(useCounterStore),
    ...mapState(useCounterStore, ["count" , "doubleCount"])
  },
  methods:{
    ...mapActions(useCounterStore, ["decrement"])
  }
}
</script>
<template>
  <div class="about">
    <hr />
    Conta<h1>{{count}}</h1>
    <hr />
    Dobro da conta<h2>{{doubleCount}}</h2>
    <hr />
    <button @click="decrement">Diminuir</button>
  </div>
</template>

<style>
</style>
