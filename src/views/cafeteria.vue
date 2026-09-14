<template>
  <ServicioDetalle
    nombre="Cafetería SENA"
    :imagen-fachada="fachada"
    descripcion=""
    :horarios="horarios"
    telefono=""
    :encargado="encargado"
  />
</template>

<script setup>
import ServicioDetalle from '../components/ServicioDetalle.vue'
import fachada from '../assets/img/cafeteria.jpg'
import fotoJefe from '../assets/img/cafeteriajefe.jpg'

const horarios = [
  { dia: 'Lunes a viernes', horario: '' }
]

const encargado = {
  foto: fotoJefe,
  nombre: 'Nombre Apellido',
  cargo: 'Coordinadora de Cafetería',
  correo: ''
}
</script>
