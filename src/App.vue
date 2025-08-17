

<template>
  <main class="contenedor-principal">
    <CitasWMB/>
    <LinksWMB/>
    <LibrosPrincipales/>
  </main>
</template>

<script setup>
import CitasWMB from './components/Citas.vue';
import LinksWMB from './components/Links.vue';
import LibrosPrincipales from './components/LibrosPrincipales.vue';
</script>

<style scoped>
.contenedor-principal{
  display:flex;
  flex-direction: column;
  gap: 60px;
}
</style>
