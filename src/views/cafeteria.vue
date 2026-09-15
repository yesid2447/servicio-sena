<template>
  <ServicioDetalle
    nombre="Cafetería SENA"
    :imagen-fachada="fachada"
    :descripcion="descripcion"
    :horarios="horarios"
    :telefono="telefono"
    :encargado="encargado"
  />
</template>

<script setup>
import ServicioDetalle from '../components/ServicioDetalle.vue'
import fachada from '../assets/img/cafeteria.jpg'
import fotoJefe from '../assets/img/cafeteriajefe.jpg'

const descripcion = "venta de comidas y demas productos para los aprendices y directivos .Ficha cocina: 3410173."

const telefono = '3223038451'

const horarios = [
  { dia: 'Lunes a viernes', horario: '7:00 a. m. - 12:00 p. m. / 1:00 p. m. - 5:30 p. m. / 7:00 p. m. - 9:30 p. m.' },
  { dia: 'Sábados', horario: '7:30 a. m. - 12:00 p. m.' }
]

const encargado = {
  foto: fotoJefe,
  nombre: 'laura carreño',
  cargo: 'Coordinadora de cafetería',
  correo: 'lcarreno@sena.edu.com'
}
</script>
