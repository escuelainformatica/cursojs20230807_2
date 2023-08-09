<script setup>
import { ref } from 'vue'

const producto = ref({ nombre: "", precio: 0, categoria: "" });
const productos = ref([]);

function agregar() {
  productos.value.push(producto.value);
  producto.value = { nombre: "", precio: 0, categoria: "" };
}

</script>

<template>
  <table>
    <thead>
      <tr>
        <th>nombre</th>
        <th>precio</th>
        <th>categoria</th>
      </tr>
    </thead>
    <tbody>
      <tr v-for="fila in productos">
        <td>{{ fila.nombre }}</td>
        <td>{{ fila.precio }}</td>
        <td>{{ fila.categoria }}</td>
      </tr>
    </tbody>
  </table>
  <hr>
  <form>
    nombre:<input type="text" v-model="producto.nombre" /><br />
    precio:<input type="text" v-model="producto.precio" /><br />
    categoria:<input type="text" v-model="producto.categoria" /><br />
    <button type="button" v-on:click="agregar">Agregar un producto nuevo</button>
  </form>
</template>

<style scoped></style>
