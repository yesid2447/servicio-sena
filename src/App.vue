<template>
  <q-layout view="hHh lpR fFf">
    <q-header elevated class="bg-green-8 text-white site-header">
      <q-toolbar class="site-toolbar">
        <q-btn dense flat round icon="menu" @click="toggleLeftDrawer" />

        <q-toolbar-title>
          <q-avatar class="header-logo bg-white">
            <img alt="Quasar logo" src="./assets/img/Logosimbolo-SENA-PRINCIPAL.png">
          </q-avatar>
          Centro Agroturístico SENA
        </q-toolbar-title>
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
      <div class="text-h5 q-pa-md">Servicios</div>

      <q-list>
        <q-item
          v-for="item in servicios"
          :key="item.to"
          clickable
          v-ripple
          :to="item.to"
          exact
          active-class="bg-green-9 text-white"
          class="bg-green-7 text-white q-mx-sm q-mb-sm rounded-borders"
        >
          <q-item-section avatar>
            <q-icon :name="item.icon" color="white" />
          </q-item-section>
          <q-item-section>{{ item.label }}</q-item-section>
        </q-item>
      </q-list>
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
.site-toolbar {
  min-height: 70px;
}

.header-logo {
  padding: 4px;
}

.services-drawer {
  background: #f6bd78;
}

:deep(.services-drawer-content) {
  background: #f6bd78;
}
</style>
