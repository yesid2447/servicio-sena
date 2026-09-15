<template>
  <ServicioDetalle
    nombre="Biblioteca"
    :imagen-fachada="fachada"
    :descripcion="descripcion"
    :horarios="horarios"
    :telefono="telefono"
    :encargado="encargado"
  />
</template>

<script setup>
import ServicioDetalle from '../components/ServicioDetalle.vue'
import fachada from '../assets/img/biblioteca.jpg'
import fotoJefe from '../assets/img/bibliotecajefe.jpg'

const descripcion = "Ofrece consultas en sala, préstamos a domicilio, préstamo interbibliotecario (PIP), talleres de lectura, capacitaciones, acceso a TIC, asesorías en búsqueda de información y asesorías en uso adecuado del catálogo bibliográfico."

const telefono = '3125848032'

const horarios = [
  { dia: 'Lunes a viernes', horario: '7:00 a. m. - 10:00 a. m.' }
]

const encargado = {
  foto: fotoJefe,
  nombre: 'Yudith Milagros Martínez Bautista',
  cargo: 'Bibliotecario',
  correo: 'ymmartinez@sena.edu.co'
}
</script>
