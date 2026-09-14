<template>
  <ServicioDetalle
    nombre="Enfermería"
    :imagen-fachada="fachada"
    descripcion=""
    :horarios="horarios"
    telefono=""
    :encargado="encargado"
  />
</template>

<script setup>
import ServicioDetalle from '../components/ServicioDetalle.vue'
import fachada from '../assets/img/enfermeria.png'
import fotoJefe from '../assets/img/enfermeriajefe.jpg'

const horarios = [
  { dia: 'Lunes a viernes', horario: '' }
]

const encargado = {
  foto: fotoJefe,
  nombre: 'Nombre Apellido',
  cargo: 'Enfermera',
  correo: ''
}
</script>
