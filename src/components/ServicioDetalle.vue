<template>
  <q-page
    class="q-pa-md sena-page"
    :style="{ backgroundImage: `url(${imagenFachada})` }"
  >
    <div class="page-overlay"></div>

    <div class="service-heading">
      <div class="heading-kicker">SERVICIO DEL CENTRO</div>
      <div class="text-h3 text-weight-bold">{{ nombre }}</div>
    </div>

    <q-card flat bordered class="q-mt-md">
      <q-card-section>
        <div class="text-subtitle1 text-green-9 text-weight-medium q-mb-xs">
          Qué ofrece este servicio
        </div>
        <p class="text-body1 q-mb-none" style="white-space: pre-line">
          {{ descripcion }}
        </p>
      </q-card-section>
    </q-card>

    <div class="row q-col-gutter-md q-mt-none">

      <div class="col-12 col-md-6">
        <q-card flat bordered>
          <q-card-section>
            <div class="text-subtitle1 text-green-9 text-weight-medium q-mb-sm">
              <q-icon name="schedule" size="20px" class="q-mr-xs" />
              Horarios de atención
            </div>
            <q-list separator>
              <q-item v-for="(h, i) in horarios" :key="i" dense>
                <q-item-section>{{ h.dia }}</q-item-section>
                <q-item-section side class="text-grey-8">{{ h.horario }}</q-item-section>
              </q-item>
            </q-list>
          </q-card-section>
        </q-card>

        <q-card flat bordered class="q-mt-md">
          <q-card-section>
            <div class="text-subtitle1 text-green-9 text-weight-medium q-mb-sm">
              <q-icon name="call" size="20px" class="q-mr-xs" />
              Contacto
            </div>
            <div class="text-body1">{{ telefono }}</div>
          </q-card-section>
        </q-card>
      </div>

      <div class="col-12 col-md-6">
        <q-card flat bordered class="full-height">
          <q-card-section class="text-center">
            <div class="text-subtitle1 text-green-9 text-weight-medium q-mb-md">
              <q-icon name="badge" size="20px" class="q-mr-xs" />
              Encargado de atención al cliente
            </div>
            <q-avatar size="110px" class="q-mb-sm">
              <img :src="encargado.foto" :alt="encargado.nombre">
            </q-avatar>
            <div class="text-h6">{{ encargado.nombre }}</div>
            <div class="text-body2 text-grey-8 q-mb-sm">{{ encargado.cargo }}</div>
            <div class="text-body2">
              <q-icon name="mail" size="16px" class="q-mr-xs" />{{ encargado.correo }}
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
  min-height: calc(100vh - 70px);
  background-position: center;
  background-size: cover;
  background-attachment: fixed;
}
.page-overlay {
  position: fixed;
  inset: 70px 0 0;
  z-index: 0;
  background: rgba(245, 249, 245, .56);
  pointer-events: none;
}
.service-heading,
.sena-page > .q-card,
.sena-page > .row {
  width: 100%;
  max-width: 1000px;
  margin-left: auto;
  margin-right: auto;
  position: relative;
  z-index: 1;
}
.service-heading {
  padding: 18px 24px 22px;
  margin-bottom: 16px;
  color: #4b2a16;
  background: rgba(238, 151, 68, .96);
  border-radius: 4px 28px 4px 28px;
  box-shadow: 0 5px 18px rgba(0, 0, 0, .14);
}
.heading-kicker {
  margin-bottom: 5px;
  color: #7e481e;
  font-size: 11px;
  font-weight: 700;
  letter-spacing: 1.4px;
}
.sena-page > .q-card {
  background: rgba(255, 255, 255, .94);
}
.sena-page > .row .q-card {
  background: rgba(255, 255, 255, .94);
}
</style>
