<script setup>
defineProps(['titulo', 'text', 'imagenes', 'showButton', 'isMainTitle', 'showImage'])
</script>

<template>
  <section class="manual-section">
   

    <h1 v-if="isMainTitle">{{ titulo }}</h1>
    
    <h2 v-else>{{ titulo }}</h2>

    <p class="cuerpo-texto">{{ text }}</p>
    
    <button v-if="showButton" class="descargar-btn">
      Descargar SVG
    </button>
    
    <div v-if="showImage" class="image-container">
      <img :src="imagenes" :alt="titulo" />
    </div>
  </section>
</template>


<style lang="scss" scoped>
@import "../style.scss";

.manual-section {
  margin-bottom: 4rem;
  padding-bottom: 2rem;

  h1 {
    @include h1-estilo;
    color: $bc-blanco; 
    margin-bottom: 2rem;
  }

  h2 {
    @include h2-estilo;
    color: $bc-azul;
    margin-bottom: 1rem;
  }

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
    border-radius: 32px;
    cursor: pointer;
    font-weight: 400;
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
    
    background: rgba(255, 255, 255, 0.05); 
    backdrop-filter: blur(12px);         
    -webkit-backdrop-filter: blur(12px);  
    
    border: 1px solid rgba(255, 255, 255, 0.1);
    
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