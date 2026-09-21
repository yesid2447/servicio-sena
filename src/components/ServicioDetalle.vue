<template>
  <q-page
    class="sena-page"
    :style="{ backgroundImage: `url(${imagenFachada})` }"
  >
    <div class="page-overlay"></div>

    <div class="content-shell">
      <div class="service-heading">
        <div class="heading-kicker">SERVICIO INSTITUCIONAL</div>
        <h1 class="service-title">{{ nombre }}</h1>
      </div>

      <div class="info-grid">
        <q-card flat class="info-card description-card">
          <q-card-section>
            <div class="card-label">
              <q-icon name="info" size="20px" class="q-mr-sm" />
              ¿Qué ofrece este servicio?
            </div>
            <p class="card-text" style="white-space: pre-line">{{ descripcion }}</p>
          </q-card-section>
        </q-card>

        <q-card flat class="info-card schedule-card">
          <q-card-section>
            <div class="card-label">
              <q-icon name="schedule" size="20px" class="q-mr-sm" />
              Horarios de atención
            </div>
            <q-list separator class="schedule-list">
              <q-item v-for="(h, i) in horarios" :key="i" dense>
                <q-item-section class="schedule-day">{{ h.dia }}</q-item-section>
                <q-item-section side class="schedule-time">{{ h.horario }}</q-item-section>
              </q-item>
            </q-list>
          </q-card-section>
        </q-card>

        <q-card flat class="info-card contact-card">
          <q-card-section>
            <div class="card-label">
              <q-icon name="call" size="20px" class="q-mr-sm" />
              Contacto
            </div>
            <div class="contact-text">{{ telefono }}</div>
          </q-card-section>
        </q-card>

        <q-card flat class="info-card profile-card">
          <q-card-section class="profile-content">
            <div class="card-label center-label">
              <q-icon name="badge" size="20px" class="q-mr-sm" />
              Encargado del servicio
            </div>

            <div class="profile-box">
              <q-avatar size="116px" class="profile-avatar">
                <img :src="encargado.foto" :alt="encargado.nombre">
              </q-avatar>

              <div class="profile-info">
                <div class="profile-name">{{ encargado.nombre }}</div>
                <div class="profile-role">{{ encargado.cargo }}</div>
                <div class="profile-mail">
                  <q-icon name="mail" size="16px" class="q-mr-sm" />
                  {{ encargado.correo }}
                </div>
              </div>
            </div>
          </q-card-section>
        </q-card>
      </div>
    </div>
  </q-page>
</template>

<script setup>
defineProps({
  nombre: { type: String, required: true },
  imagenFachada: { type: String, required: true },
  descripcion: { type: String, required: true },
  horarios: { type: Array, required: true },
  telefono: { type: String, required: true },
  encargado: { type: Object, required: true }
})
</script>

<style scoped>
.sena-page {
  width: 100%;
  max-width: none;
  margin: 0;
  position: relative;
  min-height: calc(100vh - 88px);
  background-position: center;
  background-size: cover;
  background-attachment: fixed;
  padding: 0;
  overflow: hidden;
}

.page-overlay {
  position: absolute;
  inset: 0;
  z-index: 0;
  background:
    radial-gradient(circle at 12% 12%, rgba(244, 176, 77, 0.22), transparent 22%),
    radial-gradient(circle at 88% 18%, rgba(73, 164, 112, 0.18), transparent 24%),
    linear-gradient(180deg, rgba(10, 28, 23, 0.25), rgba(10, 35, 30, 0.32));
  pointer-events: none;
}

.content-shell {
  position: relative;
  z-index: 1;
  width: min(1400px, calc(100% - 26px));
  min-height: calc(100vh - 88px);
  margin: 0 auto;
  padding: 30px 0 52px;
  display: flex;
  flex-direction: column;
}

.service-heading {
  margin-bottom: 22px;
  padding: 24px 28px;
  border-radius: 32px 12px 32px 12px;
  background: linear-gradient(135deg, #f4b04d 0%, #e88d2f 100%);
  box-shadow: 0 18px 38px rgba(22, 36, 26, 0.2);
  border: 1px solid rgba(255,255,255,0.22);
  width: 100%;
  box-sizing: border-box;
}

.heading-kicker {
  font-size: 1.15rem;
  letter-spacing: 0.22em;
  font-weight: 800;
  color: rgba(31, 39, 34, 0.8);
  margin-bottom: 10px;
}

.service-title {
  margin: 0;
  font-size: clamp(3.8rem, 6vw, 7rem);
  font-weight: 900;
  line-height: 1.04;
  letter-spacing: -0.04em;
  color: #123c2e;
}

.info-grid {
  display: grid;
  grid-template-columns: repeat(3, minmax(0, 1fr));
  grid-template-rows: minmax(260px, 1.2fr) minmax(220px, 1fr);
  gap: 22px;
  align-items: stretch;
  flex: 1;
  width: 100%;
  min-height: 620px;
}

.info-card {
  background: rgba(255, 255, 255, 0.72);
  backdrop-filter: blur(12px);
  border: 1px solid rgba(14, 53, 42, 0.08);
  border-radius: 28px;
  box-shadow: 0 18px 36px rgba(37, 58, 49, 0.10);
  overflow: hidden;
  color: #183c31;
  height: 100%;
  display: flex;
}

.info-card :deep(.q-card__section) {
  width: 100%;
  height: 100%;
  display: flex;
  flex-direction: column;
  justify-content: center;
}

.description-card {
  grid-column: 1 / -1;
  background: linear-gradient(135deg, rgba(233, 249, 239, 0.95), rgba(245, 238, 223, 0.92));
}

.schedule-card,
.contact-card,
.profile-card {
  height: 100%;
}

.card-label {
  display: flex;
  align-items: center;
  font-size: 2rem;
  font-weight: 800;
  color: #1d5d48;
  margin-bottom: 14px;
}

.center-label {
  justify-content: center;
}

.card-text {
  margin: 0;
  color: #26473d;
  line-height: 1.8;
  font-size: 1.9rem;
}

.schedule-list {
  margin-top: 8px;
  background: transparent;
}

.schedule-list .q-item {
  min-height: 48px;
  color: #edf7f1;
  border-color: rgba(255,255,255,0.08);
}

.schedule-day,
.schedule-time {
  color: #244b41;
  font-size: 1.5rem;
}

.schedule-time {
  color: #1f7a5d;
  font-weight: 700;
}

.contact-text {
  font-size: 1.8rem;
  font-weight: 800;
  color: #163d32;
}

.profile-content {
  display: flex;
  flex-direction: column;
  justify-content: center;
}

.profile-box {
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 18px;
  flex-wrap: wrap;
  text-align: center;
}

.profile-avatar {
  border: 4px solid rgba(151, 229, 179, 0.6);
  box-shadow: 0 18px 26px rgba(15, 51, 42, 0.28);
  overflow: hidden;
  display: flex;
  align-items: center;
  justify-content: center;
}

.profile-avatar img {
  width: 100%;
  height: 100%;
  object-fit: cover;
  object-position: center;
  display: block;
}

.profile-info {
  display: flex;
  flex-direction: column;
  gap: 6px;
  align-items: center;
}

.profile-name {
  font-size: 1.8rem;
  font-weight: 800;
  color: #123d34;
}

.profile-role {
  font-size: 1.4rem;
  font-weight: 700;
  color: #476d63;
}

.profile-mail {
  display: flex;
  align-items: center;
  justify-content: center;
  color: #1f7a5d;
  font-size: 1.3rem;
}

@media (max-width: 768px) {
  .info-grid {
    grid-template-columns: 1fr;
    grid-template-rows: auto;
    min-height: auto;
  }

  .description-card {
    grid-column: auto;
  }

  .content-shell {
    width: min(100%, calc(100% - 18px));
    padding-top: 18px;
  }

  .service-heading {
    padding: 18px 20px;
  }
}
</style>
