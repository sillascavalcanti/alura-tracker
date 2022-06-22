<template>
<div class="column is-2 is-justify-content-space-between is-align-items-center is-flex">
    <Cronometro :tempo-em-segundos="tempoEmSegundos"/>
    <Botao titulo="play" icon="fa-play" :desabilitado="cronometroRodando"  v-on:ao-click="iniciar"></Botao>
    <Botao titulo="stop" icon="fa-stop" :desabilitado="!cronometroRodando" v-on:ao-click="parar"></Botao>
</div>
</template>

<script lang="ts">
import { defineComponent } from 'vue'
import Cronometro from './cronometro.vue'
import Botao from './botao.vue'

export default defineComponent({
    name: 'MyCronometro',
    data() {
        return {
            tempoEmSegundos: 0,
            cronometro: 0,
            cronometroRodando:false,
        };
    },
    emits:['aoPararContador'],
    methods: {
        iniciar() {
            this.cronometroRodando=true
            this.cronometro = setInterval(() => {
                this.tempoEmSegundos += 1;
            }, 1000);
        },
        parar() {
            this.cronometroRodando=false
            clearInterval(this.cronometro);
            this.$emit('aoPararContador',this.tempoEmSegundos)
            this.tempoEmSegundos=0
        }
    },
    components: { Cronometro, Botao }
})
</script>

<style>
</style>
