<template>
  <ServicioDetalle
    nombre="Bienestar al Aprendiz"
    :imagen-fachada="fachada"
    :descripcion="descripcion"
    :horarios="horarios"
    :telefono="telefono"
    :encargado="encargado"
  />
</template>

<script setup>
import ServicioDetalle from '../components/ServicioDetalle.vue'
import fachada from '../assets/img/bienestar.jpg'
import fotoJefe from '../assets/img/bienestarjefe.jpg'

const descripcion = "Bienestar al aprendiz es una estrategia institucional para contribuir en la permanencia de los aprendices en su proceso formativo. Los servicios que presta están alineados con los objetivos estratégicos y operativos establecidos en la Política Nacional Integral de Bienestar al aprendiz, tales como el reconocimiento de la cultura como creadora de identidad, generadora de inclusión y catalizadora de diversidad; generación en los aprendices de prácticas asociadas a la prevención de la enfermedad y promoción de la salud a través de la gestión con entidades competentes (salud física y mental); fortalecimiento de habilidades blandas y para la vida; deporte, actividad física y aprovechamiento del tiempo libre como elementos fundamentales en el mejoramiento de la formación profesional integral; promoción de expresiones de arte de los aprendices en su formación profesional integral. Además de lo anterior, desde Bienestar al aprendiz se manejan temas como apoyos socioeconómicos (apoyos de sostenimiento regular, FIC, medios tecnológicos, alimentación y transporte), monitorias y fortalecimiento y ejercicio de liderazgo."

const telefono = '3176377670'

const horarios = [
  { dia: 'Enfermería - Sede Principal', horario: '6:30 a. m. - 10:30 a. m. / 4:00 p. m. - 8:00 p. m.' },
  { dia: 'Enfermería - Sede Unisangil', horario: '8:00 a. m. - 12:00 p. m. / 4:00 p. m. - 8:00 p. m.' },
  { dia: 'Apoyos socioeconómicos', horario: '8:00 a. m. - 12:00 p. m. / 2:00 p. m. - 6:00 p. m.' },
  { dia: 'Líder de Bienestar al Aprendiz', horario: '7:30 a. m. - 12:00 p. m. / 2:00 p. m. - 6:00 p. m.' }
]

const encargado = {
  foto: fotoJefe,
  nombre: 'María Delea Arenas Mejía',
  cargo: 'Líder de Bienestar al Aprendiz',
  correo: 'mdarenas@sena.edu.com'
}
</script>
