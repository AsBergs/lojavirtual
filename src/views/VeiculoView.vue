<script setup>
import { ref, reactive, onMounted } from 'vue'
import VeiculosApi from '@/api/veiculos'
import CoresApi from '@/api/cores'
import ModelosApi from '@/api/modelos'
import AcessoriosApi from '@/api/acessorios'
import Button from '../components/ButtonComponent.vue'
import NumberField from '../components/NumberComponent.vue'
import Line from '@/components/LineComponent.vue'
import Select from '../components/SelectComponent.vue'

const veiculosApi = new VeiculosApi()
const coresApi = new CoresApi()
const modelosApi = new ModelosApi()
const acessoriosApi = new AcessoriosApi()
const defaultVeiculos = { id: null, ano: '', preco: '', acessorio: '', modelo: '', cor: '' }
const veiculos = ref([])
const cores = ref([])
const modelos = ref([])
const acessorios = ref([])
const veiculo = reactive({ ...defaultVeiculos })

onMounted(async () => {
  veiculos.value = await veiculosApi.buscarTodosOsVeiculos()
  cores.value = await coresApi.buscarTodasAsCores()
  modelos.value = await modelosApi.buscarTodosOsModelos()
  acessorios.value = await acessoriosApi.buscarTodosOsAcessorios()
})

function limpar() {
  Object.assign(veiculo, { ...defaultVeiculos })
}
async function salvar() {
  if (veiculo.id) {
    await veiculosApi.atualizarVeiculo(veiculo)
  } else {
    await veiculosApi.adicionarVeiculo(veiculo)
  }
  veiculos.value = await veiculosApi.buscarTodosOsVeiculos()
  limpar()
}


</script>

<template>
  <div class="main">
    <h1>Veículos</h1>
    <div class="container-select">
      <div class="form">
        <NumberField v-model="veiculo.ano" label="ano"  />
        <NumberField v-model="veiculo.preco" label="preço"  />
        <Select v-model="veiculo.cor" label="cores" :list="cores" />
        <Select v-model="veiculo.modelo" label="modelos" :list="modelos" />
        <Select v-model="veiculo.acessorio" label="acessorios" :list="acessorios" />
        <Button @salvar="salvar()" @limpar="limpar()" />
      </div>
      <Line :veiculos="veiculos" />
    </div>
  </div>
</template>

<style>
</style>
