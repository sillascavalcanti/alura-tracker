<template>
<main class="columns is-gapless is-12">
  <div class="column is-2">
    <Barralateral/>
  </div>
  <div class="column is-10">
    <Formulario/>
  </div>
</main>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import Barralateral from './components/barralateral.vue';
import Formulario from './components/formulario.vue';

export default defineComponent({
    name: "App",
    components: { Barralateral, Formulario }
});
</script>

<style>

</style>
