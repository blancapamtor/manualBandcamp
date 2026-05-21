<script setup>
defineProps({
  texto: { type: String, default: 'Ver prototipo web de Figma →' },
  href:  { type: String, required: true },
})
</script>

<template>
  <a :href="href" target="_blank" class="boton-prototipo">{{ texto }}</a>
</template>

<style lang="scss" scoped>
@import "../style.scss";

.boton-prototipo {
  display: inline-block;
  background-color: $bc-blanco;
  color: $bc-negro;
  border: none;
  padding: 16px 36px;
  border-radius: 32px;
  cursor: pointer;
  font-family: 'Inter', sans-serif;
  font-weight: 600;
  font-size: 1.2rem;
  text-decoration: none;
  margin-top: 2rem;
  letter-spacing: 0.02em;
  transition: background 0.3s, color 0.3s;

  &:hover {
    background-color: $bc-azul-claro;
    color: $bc-azul;
  }
}
</style>
