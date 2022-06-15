<template>
    <div class="box">
        <div class="columns">
            <div class="column is-8" role="form" aria-label="Formulario para criação de um novo objeto">
                <input type="text" class="input" placeholder="Qual tarefa você iniciar?" v-model="tarefas">
            </div>
            <Temporizador @ao-parar-contador="finalizarContador"/>
        </div>
    </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue'
import Temporizador from './temporizador.vue'


export default defineComponent({
    name: "MyFormulario",
    components: { Temporizador },
    methods:{
        finalizarContador(tempoDecorrido:number) :void{
            console.log('o tempo foi',tempoDecorrido)
            console.log('a tarfa foi',this.tarefas)
            this.tarefas=''
        }
    },
    data(){
        return{
            tarefas:''
        }
    }
})
</script>

<style>
</style>
