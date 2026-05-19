<script setup>
import ManualSection from './components/ManualSection.vue'
import CardColores from './components/CardColores.vue';
const coloresBandcamp = [
  { name: 'Azul Bandcamp', hex: '2563EB', rgb: '37 99 235', hsl: '221, 83, 53', cmyk: 'c84, 58, 0, 8' },
  { name: 'Negro',         hex: '000000', rgb: '0 0 0',     hsl: '0, 0, 0',     cmyk: '0, 0, 0, 100'  },
  { name: 'Blanco',        hex: 'FAFAFA', rgb: '250 250 250', hsl: '0, 0, 98',  cmyk: '0, 0, 0, 2'    },
]
</script>

<template>
  <main>
    <section class="hero">
      <h1>Guía de estilos</h1>
      <p>Desliza y descubre</p>
    </section>

    <ManualSection 
      titulo="Identificadores" 
      text="Aquí explicamos los identificadores principales de Bandcamp."
      imagenes="src/assets/identif1.png"
      :showButton="true" 
      isMainTitle
      :showImage="true"
    />

    <ManualSection 
      titulo="Construcción" 
      text="Detalles sobre la rejilla y construcción del logo."
      imagenes="src/assets/identif2.png"
      :showImage="true"
    />

    <ManualSection 
      titulo="Submarcas" 
      text="Uso de logotipos para departamentos secundarios."
      imagenes="src/assets/identif3.png"
      :showImage="true"
    />

    <ManualSection 
      titulo="Área de respeto" 
      text="Area de respeto, texto bla bla."
      imagenes="src/assets/identif4.png"
      :showImage="true"
    />

    <ManualSection 
      titulo="Identicadores según tamaño" 
      text="Identicadores según tamaño, texto bla bla."
      imagenes="src/assets/identif5.png"
      :showImage="true"
    />

    <ManualSection 
      titulo="Identicadores según color" 
      text="Identicadores según color, texto bla bla."
      imagenes="src/assets/identif6.png"
      :showImage="true"
    />

      <ManualSection 
      titulo="Tipografía" 
      text="Nuestra tipografía principal es Inter, en nuestro sistema se incluyen 12 estilos que se adaptan a los diferentes niveles de contenido, asegurando coherencia y lectura fluida."
      isMainTitle
    />
    <ManualSection 
      titulo="Sistema" 
      imagenes="src/assets/tipo1.png"
      :showImage="true"

    />
    <ManualSection 
      titulo="Uso de tipografías" 
      imagenes="src/assets/tipo2.png"
:showImage="true"
    />
    <ManualSection
      titulo="Jerarquía según uso"
      imagenes="src/assets/tipo3.png"
      :showImage="true"
    />
    <ManualSection
      imagenes="src/assets/tipo4.png"
      :showImage="true"
    />
    <ManualSection
      imagenes="src/assets/tipo5.png"
      :showImage="true"
    />

    <CardColores
    titulo="Colores"
    text="Paleta de colores principal de Bandcamp."
    isMainTitle
    :colores="coloresBandcamp"
    imagen="src/assets/Color1.png"
    />
  </main>
</template>

<style lang="scss"> 
@import "./style.scss"; 

body {
  background-color: $bc-negro;
  color: $bc-blanco;
  margin: 0;
 
  padding: 20px 5%;
}

.hero {
  padding-top: 40px;
  height: 80vh;
  display: flex;
  flex-direction: column;
  justify-content: flex-end;
  padding-bottom: 50px;

  h1 {
    @include h1-estilo; 
    margin-bottom: 0;
    color: $bc-blanco;
  }
  
  p {
    @include cuerpo-estilo; 
    color: $bc-azul;     
  }
}
</style>