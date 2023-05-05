<script setup>

import { ref } from 'vue'




const listaCompras = ref([
{
        id: 1,
        nome: 'Camiseta',
        preco: 49.90,
        quantidade: 0,
    },
    {
        id: 2,
        nome: 'Calça',
        preco: 99.90,
        quantidade: 0,
    },
    {
        id: 3,
        nome: 'Meia',
        preco: 9.90,
        quantidade: 0,
    },
    {
        id: 4,
        nome: 'Sapato',
        preco: 199.90,
        quantidade: 0,
    },
    {
        id: 5,
        nome: 'Boné',
        preco: 29.90,
        quantidade: 0,
    },
    {
        id: 6,
        nome: 'Óculos',
        preco: 99.90,
        quantidade: 0,
    },
    {
        id: 7,
        nome: 'Relógio',
        preco: 299.90,
        quantidade: 0,
    },
    {
        id: 8,
        nome: 'Bermuda',
        preco: 79.90,
        quantidade: 0,
    },
    {
        id: 9,
        nome: 'Cueca',
        preco: 19.90,
        quantidade: 0,
    },
    {
        id: 10,
        nome: 'Meia',
        preco: 9.90,
        quantidade: 0,
    }
])

const carrinhos = ref([
{
        id: 10,
        nome: 'Meia',
        preco: 9.90,
        quantidade: 0,
    }
])

function incrementar(index) {
    listaCompras.value[index].quantidade++
  }
  function descrementar(index) {
    listaCompras.value[index].quantidade--
  }
  
  function adicionar(index) {
    carrinhos.value.push(listaCompras.value)
    carrinhos.value = ''
  }
</script>

<template>
  <div class="produtos">
    <ul>
      <li class="lista" v-for="(item, index) in listaCompras" :key="item.id">
        <p>Item: {{ item.nome }}</p>
        <p>Preco: {{ item.preco }}</p>
        <p>ID: {{ item.id }}</p>
        <p>quantidade: {{ item.quantidade }}</p>
        <button @click="incrementar(index)">+</button>
        <button @click="descrementar(index)">-</button>
        <button @click="adicionar">Adicionar</button>
      </li>
    </ul>
    <hr>
    <li v-for="item in carrinhos">
        <p>Item: {{ item.nome }}</p>
        <p>Preco: {{ item.preco }}</p>
        <p>ID: {{ item.id }}</p>
    </li>
  </div>
</template>

<style scoped></style>
