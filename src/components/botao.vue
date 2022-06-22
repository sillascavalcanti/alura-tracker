<template>
    <button class="button" @click="$emit('aoClick')" :disabled="$props.desabilitado">
        <span class="icon">
            <i class="fas " v-bind:class="icon"></i>
        </span>
        <span>{{titulo}}</span>
    </button>
</template>

<script lang="ts">
import { defineComponent } from 'vue'

export default defineComponent({
    name: 'MyBotao',
    emits:['aoClick'],
    props:{
        titulo:{
            type:String
        },
        icon:{
            type:String
        },
        desabilitado:{
            type:Boolean,
            default:false
        }
    }

})
</script>

<style>
</style>
