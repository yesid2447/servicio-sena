<template>
  <q-page class="acerca-page">
    <div class="page-background" aria-hidden="true"></div>

    <div class="content-wrapper">
      <div class="glass-panel">
        <div class="section-title text-green-9 text-weight-bold">Equipo desarrollador</div>

        <q-card flat bordered class="q-mb-lg developer-card">
          <q-card-section class="developer-content row items-center justify-center no-wrap">
            <div class="developer-text col-12 col-md">
              <div class="developer-name text-h6 text-weight-bold">{{ desarrollador.nombre }}</div>
              <div class="developer-phone text-body2 q-mt-sm">
                <q-icon name="phone" size="16px" class="q-mr-sm" />
                {{ desarrollador.contacto }}
              </div>
            </div>

            <div class="developer-avatar-wrap col-12 col-md-auto text-center">
              <q-avatar size="110px" class="developer-avatar">
                <img :src="desarrollador.foto" :alt="desarrollador.nombre">
              </q-avatar>
            </div>
          </q-card-section>
        </q-card>

        <div class="section-title text-green-9 text-weight-bold">Información del centro</div>

        <q-card flat bordered class="info-card">
          <q-card-section>
            <div class="info-item">
            <span class="label">Subdirectora del Centro:</span>
            <span class="value">Patricia Rodríguez Martínez</span>
          </div>

          <div class="info-item">
              <span class="value">Centro Agroturístico (SENA San Gil / Socorro)</span>
            </div>

            <div class="info-item">
              <span class="label">Tipo de oferta:</span>
              <span class="value">Programas técnicos, tecnólogos y cursos complementarios sin costo</span>
            </div>

            <div class="info-item">
              <span class="label">Áreas de enfoque:</span>
              <span class="value">Programas en sectores agropecuarios, turísticos, empresariales, contables y de emprendimiento rural (como campeSENA)</span>
            </div>
          </q-card-section>
        </q-card>
      </div>
    </div>
  </q-page>
</template>

<script setup>
const desarrollador = {
  foto: 'https://cdn.quasar.dev/img/boy-avatar.png',
  nombre: 'Brayan Yesid Bautista',
  contacto: '3184387090'
}
</script>

<style scoped>
.acerca-page {
  position: relative;
  width: 100%;
  max-width: none;
  margin: 0;
  min-height: calc(100vh - 70px);
  overflow: hidden;
  padding: 0;
}

.page-background {
  position: absolute;
  inset: 0;
  background-image: url('../assets/img/senasangil.jpg');
  background-size: cover;
  background-position: center;
  background-repeat: no-repeat;
  filter: brightness(1.1) saturate(0.9) contrast(0.95);
  transform: scale(1.03);
}

.content-wrapper {
  position: relative;
  z-index: 1;
  width: 100%;
  max-width: 1100px;
  margin: 0 auto;
  padding: 24px 20px 30px;
}

.glass-panel {
  background: rgba(255, 255, 255, 0.78);
  border: 1px solid rgba(255, 255, 255, 0.7);
  border-radius: 18px;
  box-shadow: 0 10px 25px rgba(0, 0, 0, 0.08);
  backdrop-filter: blur(3px);
  padding: 22px 18px;
}

.section-title {
  font-size: 1.35rem;
  margin-bottom: 12px;
  font-weight: 700;
  letter-spacing: 0.02em;
}

.developer-card,
.info-card {
  border-radius: 14px;
  background: rgba(255, 255, 255, 0.94);
  border: 1px solid rgba(0, 0, 0, 0.08);
}

.developer-card {
  width: min(90%, 620px);
  margin-left: auto;
  margin-right: auto;
}

.developer-content {
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 20px;
  text-align: center;
  width: 100%;
}

.developer-text {
  text-align: center;
  padding-right: 0;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
}

.developer-name {
  color: #1f3f2a;
}

.developer-phone {
  color: #2e7d32;
  font-weight: 600;
  display: flex;
  align-items: center;
  justify-content: center;
  text-align: center;
}

.developer-avatar-wrap {
  display: flex;
  justify-content: center;
  align-items: center;
  width: 100%;
  margin-top: 8px;
}

.developer-avatar {
  border: 3px solid #2e7d32;
  box-shadow: 0 8px 16px rgba(46, 125, 50, 0.18);
  margin: 0 auto;
}

.info-item {
  display: flex;
  flex-direction: column;
  gap: 4px;
  padding: 12px 0;
  border-bottom: 1px solid #e0e0e0;
}

.info-item:last-child {
  border-bottom: none;
  padding-bottom: 0;
}

.label {
  font-weight: 700;
  color: #2e7d32;
}

.value {
  color: #333;
  line-height: 1.6;
}
</style>
