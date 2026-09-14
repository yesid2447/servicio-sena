<template>
  <ServicioDetalle
    nombre="Coordinación Académica"
    :imagen-fachada="fachada"
    descripcion=""
    :horarios="horarios"
    telefono=""
    :encargado="encargado"
  />
</template>

<script setup>
import ServicioDetalle from '../components/ServicioDetalle.vue'
import fachada from '../assets/img/coordinacion.jpg'
import fotoJefe from '../assets/img/coordinacionjefe.jpg'

const horarios = [
  { dia: 'Lunes a viernes', horario: '' }
]

const encargado = {
  foto: fotoJefe,
  nombre: 'Nombre Apellido',
  cargo: 'Coordinador Académico',
  correo: ''
}
</script>
