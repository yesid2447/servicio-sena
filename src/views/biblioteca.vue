<template>
  <ServicioDetalle
    nombre="Biblioteca"
    :imagen-fachada="fachada"
    descripcion=""
    :horarios="horarios"
    telefono=""
    :encargado="encargado"
  />
</template>

<script setup>
import ServicioDetalle from '../components/ServicioDetalle.vue'
import fachada from '../assets/img/biblioteca.jpg'
import fotoJefe from '../assets/img/bibliotecajefe.jpg'

const horarios = [
  { dia: 'Lunes a viernes', horario: '' }
]

const encargado = {
  foto: fotoJefe,
  nombre: 'Nombre Apellido',
  cargo: 'Bibliotecaria',
  correo: ''
}
</script>
