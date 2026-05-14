<script setup>
// Lo añadimos aquí igual que el showButton
defineProps(['titulo', 'text', 'imagenes', 'showButton', 'isMainTitle'])
</script>

<template>
  <section class="manual-section">
   

    <h1 v-if="isMainTitle">{{ titulo }}</h1>
    
    <h2 v-else>{{ titulo }}</h2>

    <p class="cuerpo-texto">{{ text }}</p>
    
    <button v-if="showButton" class="descargar-btn">
      Descargar SVG
    </button>
    
    <div class="image-container">
      <img :src="imagenes" :alt="titulo" />
    </div>
  </section>
</template>


<style lang="scss" scoped>
// Importamos las variables y mixins
@import "../style.scss";

.manual-section {
  margin-bottom: 4rem;
  padding-bottom: 2rem;

  // Aplicamos el mixin de H1 y lo ponemos en blanco
  h1 {
    @include h1-estilo;
    color: $bc-blanco; 
    margin-bottom: 2rem;
  }

  // Aplicamos el mixin de H2 (Título 2)
  h2 {
    @include h2-estilo;
    color: $bc-azul;
    margin-bottom: 1rem;
  }

  // Aplicamos el mixin del cuerpo de texto
  .cuerpo-texto {
    @include cuerpo-estilo;
    color: $bc-blanco;
    max-width: 800px;
  }

  .descargar-btn {
    background-color: $bc-azul;
    color: $bc-blanco;
    border: none;
    padding: 12px 24px;
    border-radius: 4px;
    cursor: pointer;
    font-weight: 700;
    margin: 1rem 0;
    transition: background 0.3s;

    &:hover {
      background-color: $bc-azul-oscuro;
    }
  }

  .image-container {
    margin-top: 2rem;
    img {
      max-width: 100%;
      height: auto;
      display: block;
    }
  }

  .glass-card {
    margin-top: 3rem;
    padding: 2rem;
    border-radius: 16px;
    
    // El efecto cristal:
    background: rgba(255, 255, 255, 0.05); // Blanco casi invisible
    backdrop-filter: blur(12px);           // El desenfoque del fondo
    -webkit-backdrop-filter: blur(12px);   // Compatibilidad para Safari
    
    // Un borde sutil para que parezca cristal
    border: 1px solid rgba(255, 255, 255, 0.1);
    
    // Sombra suave para dar profundidad
    box-shadow: 0 8px 32px 0 rgba(0, 0, 0, 0.37);

    p {
        @include cuerpo-estilo;
      margin: 0;
      color: $bc-blanco;
      font-weight: 500;
    }
  }

}
</style>