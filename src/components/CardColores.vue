<template>
  <section class="manual-section color-section">
    <!-- Título principal (isMainTitle) -->
    <h2 v-if="isMainTitle && titulo" class="section-main-title">{{ titulo }}</h2>
    <h3 v-else-if="titulo" class="section-title">{{ titulo }}</h3>

    <!-- Texto descriptivo -->
    <p v-if="text" class="section-text">{{ text }}</p>

    <!-- Cards de color -->
    <div class="color-cards-grid">
      <div 
        v-for="color in colores"
        :key="color.hex"
        class="color-card"
        :class="{ 'color-card--compact': props.compact }"
        :style="{ backgroundColor: `#${color.hex}` }"
        @click="copyHex(color.hex)"
      >
        <div class="card-header">
          <span class="color-name" :style="{ color: getTextColor(color.hex) }">
            {{ color.name }}
          </span>
        </div>

        <transition name="toast">
          <div v-if="copiedHex === color.hex" class="toast">¡Copiado! #{{ color.hex }}</div>
        </transition>

        <div class="card-info">
          <div
            v-for="row in infoRows(color)"
            :key="row.label"
            class="info-row"
            :style="{ borderTopColor: getBorderColor(color.hex), color: getTextColor(color.hex) }"
          >
            <span class="label">{{ row.label }}</span>
            <span class="value">{{ row.value }}</span>
          </div>
        </div>
      </div>
    </div>

    <!-- Imagen debajo de las cards (opcional) -->
    <img v-if="imagen" :src="imagen" class="section-image" alt="" />
  </section>
</template>

<script setup>
import { ref } from 'vue'

const props = defineProps({
  titulo:      { type: String,  default: '' },
  text:        { type: String,  default: '' },
  isMainTitle: { type: Boolean, default: false },
  imagen:      { type: String,  default: '' },  
  compact:     { type: Boolean, default: false },
  colores: {
    type: Array,
    default: () => [
      { name: 'Azul Bandcamp', hex: '2563EB', rgb: '37 99 235', hsl: '221, 83, 53', cmyk: 'c84, 58, 0, 8' },
      { name: 'Negro',         hex: '000000', rgb: '0 0 0',     hsl: '0, 0, 0',     cmyk: '0, 0, 0, 100'  },
      { name: 'Blanco',        hex: 'FAFAFA', rgb: '250 250 250', hsl: '0, 0, 98',  cmyk: '0, 0, 0, 2'    },
    ],
  },
})

const copiedHex = ref(null)


function infoRows(color) {
  const all = [
    { label: 'HEX',  value: color.hex  },
    { label: 'RGB',  value: color.rgb  },
    { label: 'HSL',  value: color.hsl  },
    { label: 'CMYK', value: color.cmyk },
  ]
  return props.compact ? all.slice(0, 2) : all
}

function getLuminance(hex) {
  const r = parseInt(hex.substring(0, 2), 16)
  const g = parseInt(hex.substring(2, 4), 16)
  const b = parseInt(hex.substring(4, 6), 16)
  return (0.299 * r + 0.587 * g + 0.114 * b) / 255
}

function getTextColor(hex) {
  return getLuminance(hex) > 0.55 ? '#111111' : '#ffffff'
}

function getBorderColor(hex) {
  return getLuminance(hex) > 0.55 ? 'rgba(0,0,0,0.12)' : 'rgba(255,255,255,0.25)'
}

async function copyHex(hex) {
  try {
    await navigator.clipboard.writeText(`#${hex}`)
  } catch {
    const el = document.createElement('textarea')
    el.value = `#${hex}`
    document.body.appendChild(el)
    el.select()
    document.execCommand('copy')
    document.body.removeChild(el)
  }
  copiedHex.value = hex
  setTimeout(() => (copiedHex.value = null), 1800)
}
</script>

<style lang="scss">
@import "../style.scss";
.color-section {
  padding: 40px 0;
}

/* Reutiliza los mismos estilos de título/texto que ManualSection */
.section-main-title {
    @include h2-estilo;
    color: $bc-azul;
    margin-bottom: 1rem;
    
  }

.section-title {
    @include h1-estilo;
    color: $bc-blanco; 
    margin-bottom: 2rem;
 
}

.section-text {
   
    @include cuerpo-estilo;
    color: $bc-blanco;
    max-width: 800px;
  
}



  
/* Grid de cards */
.color-cards-grid {
  display: flex;
  flex-direction: row;
  flex-wrap: wrap;
  gap: 32px;
  margin-bottom: 40px;
  width: 100%;
  overflow: visible;
}

/* Card */
/* Card */
.color-card {
  position: relative;
  width: 260px;
  min-width: 200px;
  min-height: 340px;
  border-radius: 20px;
  padding: 20px 24px 24px;
  cursor: pointer;
  user-select: none;
  display: flex;
  flex-direction: column;
  box-shadow: 0 8px 32px rgba(0, 0, 0, 0.25);
  transition: transform 0.15s ease, box-shadow 0.15s ease;
  flex-shrink: 0;

  &:hover {
    transform: translateY(-4px) scale(1.01);
    box-shadow: 0 16px 44px rgba(0, 0, 0, 0.32);
  }

  &:active {
    transform: scale(0.97);
  }

  &.color-card--compact {
  min-height: 170px;
  padding: 16px 20px 18px;
}

:deep(.color-card--compact .card-info) {
  padding-top: 20px;
  gap: 6px;
}

:deep(.color-card--compact .info-row) {
  padding-top: 6px;
}

:deep(.color-card--compact .label),
:deep(.color-card--compact .value) {
  font-size: 11px;
}

:deep(.color-card--compact .color-name) {
  font-size: 13px;
}
}
.card-header {
  flex: 1;
}

.color-name {
    font-family: 'Inter', sans-serif;
  font-weight: 700;
  font-size: 15px;
}

/* Toast */
.toast {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  background: rgba(0, 0, 0, 0.6);
  backdrop-filter: blur(6px);
  color: #fff;
  font-family: 'Inter', sans-serif;
  font-size: 14px;
  font-weight: 600;
  padding: 10px 20px;
  border-radius: 50px;
  white-space: nowrap;
  pointer-events: none;
}

.toast-enter-active,
.toast-leave-active {
  transition: opacity 0.25s ease, transform 0.25s ease;
}
.toast-enter-from,
.toast-leave-to {
  opacity: 0;
  transform: translate(-50%, -40%);
}

/* Info rows */
.card-info {

font-family: 'Inter', sans-serif;
  display: flex;
  flex-direction: column;
  gap: 10px;
  margin-top: auto;
  padding-top: 80px;
}

.info-row {
    font-family: 'Inter', sans-serif;
  display: flex;
  justify-content: space-between;
  align-items: center;
  border-top: 1px solid;
  padding-top: 10px;
}

.label {
    font-family: 'Inter', sans-serif;
  font-size: 13px;
  font-weight: 600;
  letter-spacing: 0.04em;
}

.value {
    font-family: 'Inter', sans-serif;
  font-size: 13px;
  font-weight: 400;
}

/* Imagen opcional debajo */
.section-image {

  width: 100%;
  border-radius: 12px;
  display: block;
}


</style>