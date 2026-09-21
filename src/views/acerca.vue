<template>
  <q-page class="acerca-page">
    <div class="page-background" aria-hidden="true"></div>

    <div class="content-wrapper">
      <div class="glass-panel">
        <div class="section-header">
          <div class="section-badge">Institucional</div>
          <h2 class="section-title">Equipo desarrollador</h2>
        </div>

        <q-card flat class="developer-card">
          <q-card-section class="developer-content">
            <div class="developer-avatar-wrap">
              <q-avatar size="112px" class="developer-avatar">
                <img :src="desarrollador.foto" :alt="desarrollador.nombre">
              </q-avatar>
            </div>

            <div class="developer-text">
              <div class="developer-name">{{ desarrollador.nombre }}</div>
              <div class="developer-phone">
                <q-icon name="phone" size="16px" class="q-mr-sm" />
                {{ desarrollador.contacto }}
              </div>
            </div>
          </q-card-section>
        </q-card>

        <div class="section-header section-header-space">
          <div class="section-badge">Centro</div>
          <h2 class="section-title">Información del centro</h2>
        </div>

        <q-card flat class="info-card">
          <q-card-section>
            <div class="info-item">
              <span class="label">Subdirectora del Centro:</span>
              <span class="value">Patricia Rodríguez Martínez</span>
            </div>

            <div class="info-item">
              <span class="label">Ubicación:</span>
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
  min-height: calc(100vh - 88px);
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
  filter: brightness(0.74) saturate(1.15) contrast(1.08);
  transform: scale(1.05);
}

.content-wrapper {
  position: relative;
  z-index: 1;
  width: min(1100px, calc(100% - 24px));
  margin: 0 auto;
  padding: 40px 0 46px;
}

.glass-panel {
  background: linear-gradient(135deg, rgba(255, 255, 255, 0.72), rgba(238, 246, 241, 0.64));
  border: 1px solid rgba(14, 53, 42, 0.08);
  border-radius: 32px;
  box-shadow: 0 28px 50px rgba(8, 17, 19, 0.12);
  backdrop-filter: blur(10px);
  padding: 28px 22px;
}

.section-header {
  margin-bottom: 18px;
}

.section-header-space {
  margin-top: 30px;
}

.section-badge {
  display: inline-block;
  padding: 7px 12px;
  border-radius: 999px;
  background: rgba(244, 176, 77, 0.18);
  color: #955d15;
  font-size: 0.64rem;
  font-weight: 800;
  letter-spacing: 0.14em;
  text-transform: uppercase;
}

.section-title {
  margin: 12px 0 0;
  font-size: clamp(1.8rem, 2.4vw, 2.6rem);
  font-weight: 900;
  line-height: 1.1;
  color: #183f34;
}

.developer-card,
.info-card {
  border-radius: 26px;
  background: linear-gradient(135deg, rgba(255,255,255,0.9), rgba(236,246,240,0.9));
  border: 1px solid rgba(14, 53, 42, 0.08);
  box-shadow: 0 18px 34px rgba(6, 17, 20, 0.08);
}

.developer-card {
  width: min(700px, 100%);
  margin: 0 auto 8px;
}

.developer-content {
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 22px;
  flex-wrap: wrap;
  text-align: center;
  padding: 22px 18px;
}

.developer-avatar-wrap {
  display: flex;
  justify-content: center;
}

.developer-avatar {
  border: 4px solid rgba(244, 176, 77, 0.52);
  box-shadow: 0 18px 28px rgba(12, 22, 17, 0.22);
}

.developer-text {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
}

.developer-name {
  font-size: 1.38rem;
  font-weight: 800;
  color: #123f35;
}

.developer-phone {
  display: flex;
  align-items: center;
  justify-content: center;
  margin-top: 8px;
  color: #1d6f59;
  font-weight: 700;
}

.info-item {
  display: flex;
  flex-direction: column;
  gap: 5px;
  padding: 14px 0;
  border-bottom: 1px solid rgba(255,255,255,0.08);
}

.info-item:last-child {
  border-bottom: none;
  padding-bottom: 0;
}

.label {
  font-weight: 800;
  color: #a7651a;
}

.value {
  color: #1f3a34;
  line-height: 1.7;
}
</style>
