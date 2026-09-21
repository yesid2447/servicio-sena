<template>
  <q-layout view="hHh lpR fFf">
    <q-header elevated class="site-header">
      <q-toolbar class="site-toolbar">
        <q-btn
          flat
          round
          dense
          icon="menu"
          class="menu-button"
          @click="toggleLeftDrawer"
        />

        <div class="brand-block">
          <q-avatar class="header-logo">
            <img alt="Logo SENA" src="./assets/img/Logosimbolo-SENA-PRINCIPAL.png">
          </q-avatar>

          <div class="brand-copy">
            <div class="brand-title">Centro Agroturístico</div>
            <div class="brand-subtitle">SENA San Gil</div>
          </div>
        </div>
      </q-toolbar>
    </q-header>

    <q-drawer
      v-model="leftDrawerOpen"
      side="left"
      overlay
      behavior="mobile"
      bordered
      class="services-drawer"
      content-class="services-drawer-content"
    >
      <div class="drawer-panel">
        <div class="drawer-header">
          <span class="drawer-title">Servicios</span>
          <span class="drawer-tag">Navegación</span>
        </div>

        <q-list class="drawer-list" separator>
          <q-item
            v-for="item in servicios"
            :key="item.to"
            clickable
            v-ripple
            :to="item.to"
            exact
            active-class="drawer-item-active"
            class="drawer-item"
          >
            <q-item-section avatar>
              <q-icon :name="item.icon" class="drawer-icon" />
            </q-item-section>
            <q-item-section class="drawer-label">{{ item.label }}</q-item-section>
          </q-item>
        </q-list>
      </div>
    </q-drawer>

    <q-page-container>
      <router-view />
    </q-page-container>
  </q-layout>
</template>

<script setup>
import { ref } from 'vue'

const leftDrawerOpen = ref(false)
function toggleLeftDrawer () {
  leftDrawerOpen.value = !leftDrawerOpen.value
}

const servicios = [
  { label: 'Enfermería', to: '/', icon: 'local_hospital' },
  { label: 'Bienestar', to: '/bienestar', icon: 'favorite' },
  { label: 'Biblioteca', to: '/biblioteca', icon: 'menu_book' },
  { label: 'Cafetería', to: '/cafeteria', icon: 'restaurant' },
  { label: 'Coordinación', to: '/coordinacion', icon: 'groups' },
  { label: 'Acerca', to: '/acerca', icon: 'info' }
]
</script>

<style scoped>
.site-header {
  background: linear-gradient(135deg, #0e4f3a 0%, #1f6a4d 42%, #1a5d49 100%);
  backdrop-filter: blur(18px);
  border-bottom: 1px solid rgba(255, 255, 255, 0.08);
  box-shadow: 0 14px 36px rgba(12, 69, 48, 0.22);
}

.site-toolbar {
  min-height: 108px;
  padding: 0 18px;
}

.menu-button {
  color: #f7c76a;
  background: rgba(255, 255, 255, 0.06);
  border: 1px solid rgba(247, 199, 106, 0.22);
  box-shadow: 0 10px 25px rgba(0, 0, 0, 0.18);
  width: 52px;
  height: 52px;
}

.brand-block {
  display: flex;
  align-items: center;
  gap: 16px;
  margin-left: 14px;
  padding: 8px 16px 8px 8px;
  border-radius: 999px;
  background: linear-gradient(135deg, rgba(255,255,255,0.10), rgba(255,255,255,0.03));
  border: 1px solid rgba(255,255,255,0.08);
}

.header-logo {
  width: 70px;
  height: 70px;
  padding: 0;
  background: linear-gradient(135deg, #ffffff 0%, #edf7f0 100%);
  border: 3px solid #f4b04d;
  box-shadow: 0 12px 28px rgba(244, 176, 77, 0.28);
  overflow: hidden;
  display: flex;
  align-items: center;
  justify-content: center;
}

.header-logo img {
  width: 100%;
  height: 100%;
  object-fit: contain;
  object-position: center;
  display: block;
  padding: 8px;
}

.brand-copy {
  display: flex;
  flex-direction: column;
  justify-content: center;
}

.brand-title {
  font-size: 1.28rem;
  font-weight: 800;
  letter-spacing: 0.04em;
  color: #f8f5f0;
}

.brand-subtitle {
  font-size: 0.78rem;
  letter-spacing: 0.18em;
  text-transform: uppercase;
  color: #d2efd8;
}

.services-drawer {
  background: linear-gradient(180deg, #0d3f2b 0%, #144a36 100%);
  box-shadow: 0 22px 40px rgba(8, 29, 21, 0.35);
}

:deep(.services-drawer-content) {
  background: linear-gradient(180deg, #0d3f2b 0%, #144a36 100%);
}

:deep(.q-drawer__content) {
  background: linear-gradient(180deg, #0d3f2b 0%, #144a36 100%);
}

:deep(.q-item) {
  color: #edf7f1 !important;
  background: transparent !important;
}

.drawer-panel {
  padding: 18px 14px 20px;
}

.drawer-header {
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding: 12px 12px 16px;
  margin-bottom: 12px;
  border-bottom: 1px solid rgba(255, 255, 255, 0.10);
}

.drawer-title {
  color: #f6f1e8;
  font-size: 1.4rem;
  font-weight: 700;
}

.drawer-tag {
  background: linear-gradient(135deg, rgba(244,176,77,0.18), rgba(72,145,102,0.12));
  color: #f7c76a;
  font-size: 0.6rem;
  letter-spacing: 0.12em;
  text-transform: uppercase;
  border-radius: 999px;
  padding: 7px 10px;
}

.drawer-list {
  background: transparent;
}

.drawer-item {
  margin: 8px 0;
  border-radius: 18px;
  color: #edf7f1;
  background: rgba(255, 255, 255, 0.06);
  transition: all 0.25s ease;
  border: 1px solid rgba(255, 255, 255, 0.10);
  box-shadow: inset 0 1px 0 rgba(255,255,255,0.04);
}

.drawer-item:hover {
  background: rgba(255, 255, 255, 0.12);
  transform: translateX(4px);
}

.drawer-icon {
  color: #f7c76a;
}

.drawer-label {
  font-weight: 700;
  color: #edf7f1;
}

.drawer-item-active {
  background: linear-gradient(135deg, #f4b04d 0%, #df8d2f 100%) !important;
  color: #163f30 !important;
  box-shadow: 0 14px 34px rgba(223, 141, 47, 0.28);
  border-color: rgba(255,255,255,0.22);
}

.drawer-item-active .drawer-icon {
  color: #163f30 !important;
}
</style>
