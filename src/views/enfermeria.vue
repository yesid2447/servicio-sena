<template>
  <ServicioDetalle
    nombre="Enfermería"
    :imagen-fachada="fachada"
    :descripcion="descripcion"
    :horarios="horarios"
    :telefono="telefono"
    :encargado="encargado"
  />
</template>

<script setup>
import ServicioDetalle from '../components/ServicioDetalle.vue'
import fachada from '../assets/img/enfermeria.png'
import fotoJefe from '../assets/img/enfermeriajefe.jpg'

const descripcion = "Aquí se ofrece todos los servicios de promoción y prevención de enfermedades, así como atención básica en primeros auxilios."

const telefono = '3214153995'

const horarios = [
  { dia: 'Lunes a viernes', horario: '6:30 a. m. - 10:30 a. m. / 4:00 p. m. - 8:00 p. m.' }
]

const encargado = {
  foto: fotoJefe,
  nombre: 'María Fernanda Gómez Reyes',
  cargo: 'Enfermera',
  correo: 'Mafecita1118@gmail.com'
}
</script>
