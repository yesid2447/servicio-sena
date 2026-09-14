<template>
  <ServicioDetalle
    nombre="Bienestar al Aprendiz"
    :imagen-fachada="fachada"
    descripcion="Bienestar al Aprendiz es una estrategia institucional para contribuir a la permanencia de los aprendices en su proceso formativo."
    :horarios="horarios"
    telefono=""
    :encargado="encargado"
  />
</template>

<script setup>
import ServicioDetalle from '../components/ServicioDetalle.vue'
import fachada from '../assets/img/bienestar.jpg'
import fotoJefe from '../assets/img/bienestarjefe.jpg'

const horarios = [
  { dia: 'Sede Principal', horario: '' },
  { dia: 'Sede Unisangil', horario: '' }
]

const encargado = {
  foto: fotoJefe,
  nombre: 'Nombre Apellido',
  cargo: 'Líder de Bienestar al Aprendiz',
  correo: ''
}
</script>
