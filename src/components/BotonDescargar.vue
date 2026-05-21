<script setup>
defineProps({
  texto: { type: String, default: 'Descargar SVG' },
  href:  { type: String, default: '' },
})
</script>

<template>
  <a v-if="href" :href="href" download class="descargar-btn">{{ texto }}</a>
  <button v-else class="descargar-btn">{{ texto }}</button>
</template>

<style lang="scss" scoped>
@import "../style.scss";

.descargar-btn {
  display: inline-block;
  background-color: $bc-azul;
  color: $bc-blanco;
  border: none;
  padding: 12px 24px;
  border-radius: 32px;
  cursor: pointer;
  font-family: 'Inter', sans-serif;
  font-weight: 400;
  font-size: 1rem;
  text-decoration: none;
  margin: 1rem 0;
  transition: background 0.3s;

  &:hover {
    background-color: $bc-azul-oscuro;
  }
}
</style>
