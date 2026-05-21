<script setup>
import ManualSection from './components/ManualSection.vue'
import CardColores from './components/CardColores.vue'
import BotonDescargar from './components/BotonDescargar.vue'
import BotonPrototipo from './components/BotonPrototipo.vue'
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
      <BotonPrototipo
        href="https://www.figma.com/proto/fxkAySOek8JCagCuoJGoNu/SistemaDise%C3%B1o_Bandcamp?node-id=1178-1039&t=OejKozrqSsXrbHDn-1"
      />
    </section>

    <ManualSection
      titulo="Identificadores"
      text="Aquí explicamos los identificadores principales de Bandcamp."
      imagenes="src/assets/identif1.png"
      isMainTitle
      :showImage="true"
    >
      <BotonDescargar texto="Descargar SVG" />
    </ManualSection>

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
   
    <ManualSection 
      titulo="Uso de colores" 
      text="Estas guías muestran el uso de la paleta según los diferentes contextos."
      imagenes="src/assets/Color2.png"
      :showImage="true"

    />
     <ManualSection 
      titulo="Paleta de neutrales" 
      text="Nuestra paleta de neutrales aporta balance, claridad y accesibilidad. Además sirve para complementar la paleta principal."
      imagenes="src/assets/Color3.png"
      :showImage="true"

    />
    <CardColores
    titulo="Paleta neutrales"
    text="Nuestra paleta de neutrales aporta balance, claridad y accesibilidad. Además sirve para complementar la paleta principal."
    :colores="coloresBandcamp"
     compact
/>
    <ManualSection 
      titulo="Porcentaje de color" 
      text="Nuestra paleta sigue unos porcentajes de color para su uso. Esto aporta claridad y continuidad."
      imagenes="src/assets/Color4.png"
      :showImage="true"

    />
    <ManualSection 
      titulo="Uso del color con texto" 
      text="Para asegurar legibilidad de los textos aplicados a nuestros colores hay que seguir esta guía."
      imagenes="src/assets/Color5.png"
      :showImage="true"

    />
    <ManualSection 
      titulo="Degradado Bandcamp" 
      text="Al igual que los géneros Bandcamp tiene su propio degradado. Este se usa en diferentes aplicaciones."
      imagenes="src/assets/Color6.png"
      :showImage="true"

    />
    <ManualSection 
      titulo="Uso del degradado" 
      text="Utilizamos el degradado como separador y/o como elemento gráfico."
      imagenes="src/assets/Color6.png"
      :showImage="true"

    />
    <ManualSection 
      titulo="Usos del degradado Bandcamp" 
      text="Utilizamos el degradado como separador y/o como elemento gráfico."
      imagenes="src/assets/Color7.png"
      :showImage="true"

    />
    <ManualSection 
      titulo="Elementos gráficos" 
      text="El uso del imagotipo, logotipo e isotipo se define por la escala y el soporte. La marca varía según el tamaño para garantizar siempre su legibilidad."
      isMainTitle
    />
    <ManualSection 
      titulo="Cimática" 
      text="Nuestro sistema emplea texturas de partículas basadas en la cimática que visualizan el sonido en tiempo real. Estas reaccionan directamente al audio de la web, transformando su forma según la onda y su color según el género musical, apoyadas por un sistema de degradados. Su uso es puntual y estratégico para enriquecer la identidad visual sin saturar la estética general."
      imagenes="src/assets/degradado1.png"
      :showImage="true"
    />
     <ManualSection 
      titulo="Degradados" 
      text="Creamos un sistema de degradados que funcionan como complemento visual para las texturas y su diferenciación, estos se basan en aquello que representa cada estilo de música, sigueindo la psicología del color. "
      imagenes="src/assets/degradado2.png"
      :showImage="true"

    />

    <ManualSection 
      titulo="Márgenes" 
      text="Los márgenes establecen una base, que asegura que el contenido se mantenga legible, uniforme y ordenado en todos los formatos. Nuestro sistema se adapta al formato de visualización, definiendo dos márgenes estándar: uno específico para pantallas horizontales (large) y otro ajustado para pantallas verticales (small). "
      imagenes="src/assets/Margenes.png"
      :showImage="true"

    />
    <ManualSection 
      titulo="Columnas" 
      text="La cantidad de columnas también se adaptan al formato de visualización, definiendo 12 columnas para pantallas horizontales (large) y 2 columnas para pantallas verticales (small).  "
      imagenes="src/assets/columnas.png"
      :showImage="true"

    />
    <ManualSection 
      titulo="Guías" 
      text="Estas son las guías usadas para que nuestras cards tengan un margen y espacio para respirar dependiendo de su tamaño.  "
      imagenes="src/assets/guias.png"
      :showImage="true"

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