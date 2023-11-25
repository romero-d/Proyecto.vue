<template>
  <div>
    <h1 v-if="mostrarTitulo" style="color: gray;">Rompecabezas de las Estaciones del Año</h1>
    <button class="boton primavera" @click="mostrarComponenteHijo('Primavera')">Primavera</button>
    <button class="boton verano" @click="mostrarComponenteHijo('Verano')">Verano</button>
    <button class="boton otono" @click="mostrarComponenteHijo('Estacion3')">Otoño</button>
    <button class="boton invierno" @click="mostrarComponenteHijo('Invierno')">Invierno</button>

    <Primavera v-if="mostrarHijo === 'Primavera'" @cerrar="ocultarComponenteHijo" />
    <Verano v-if="mostrarHijo === 'Verano'" @cerrar="ocultarComponenteHijo" />
    <Estacion3 v-if="mostrarHijo === 'Estacion3'" @cerrar="ocultarComponenteHijo" />
    <Invierno v-if="mostrarHijo === 'Invierno'" @cerrar="ocultarComponenteHijo" />
  </div>
</template>

<script setup>
import { ref } from 'vue';
import Verano from './components/Verano.vue';
import Invierno from './components/Invierno.vue';
import Estacion3 from './components/Estacion3.vue'
import Primavera from './components/Primavera.vue';

const mostrarHijo = ref(null);
const mostrarTitulo = ref(true);

const mostrarComponenteHijo = (nombreComponente) => {
  mostrarHijo.value = nombreComponente;
  mostrarTitulo.value = false; 
};

const ocultarComponenteHijo = () => {
  mostrarHijo.value = null;
};

</script>

<style scoped>
.boton{
  color: white;
  border: 2px solid transparent;
  padding: 10px 20px;
  text-align: center;
  text-decoration: none;
  display: inline-block;
  font-size: 16px;
  margin: 4px 2px;
  transition-duration: 0.4s;
  cursor: pointer;
  border-radius: 8px;
}

.primavera {
  background-color: #4CAF50; 
}

.verano {
  background-color: #2196F3; 
}

.otono {
  background-color: #FF9800; 
}

.invierno {
  background-color: #607D8B; 
}
.boton:hover {
  color: black;
  border: 2px solid white;
}
</style>