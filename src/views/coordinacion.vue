<template>
  <ServicioDetalle
    nombre="Coordinación Académica"
    :imagen-fachada="fachada"
    :descripcion="descripcion"
    :horarios="horarios"
    :telefono="telefono"
    :encargado="encargado"
  />
</template>

<script setup>
import ServicioDetalle from '../components/ServicioDetalle.vue'
import fachada from '../assets/img/coordinacion.jpg'
import fotoJefe from '../assets/img/coordinacionjefe.jpg'

const descripcion = "Apoyamos el tema de novedades de los aprendices, retiros, deserción, trámite de aplazamientos que corresponden a la formación titulada del SENA. También se apoya con el tema de la programación de los instructores para la formación y la logística de los ambientes para que estén en óptimas condiciones."

const telefono = '3166783027'

const horarios = [
  { dia: 'Lunes a viernes', horario: '7:30 a. m. - 12:00 p. m.' }
]

const encargado = {
  foto: fotoJefe,
  nombre: 'Luis Carlos Reina',
  cargo: 'Coordinador académico',
  correo: 'lreinas@sena.edu.com'
}
</script>
