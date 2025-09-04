<template>
  <div class="container mt-5">
    <h2 class="mb-4">Formulario de Registro</h2>

    <form @submit.prevent>
      <div class="mb-3">
        <label for="nombre" class="form-label">Nombre</label>
        <input type="text" id="nombre" class="form-control" v-model="nombre">
      </div>

      <div class="mb-3">
        <label for="correo" class="form-label">Correo electrónico</label>
        <input type="email" id="correo" class="form-control" v-model="correo">
      </div>

      <div class="mb-3">
        <label for="edad" class="form-label">Edad</label>
        <input type="number" id="edad" class="form-control" v-model="edad">
      </div>

      <button type="button" class="btn btn-primary me-2" @click="mostrarResumen">Mostrar resumen</button>
      <button type="button" class="btn btn-secondary" @click="limpiarFormulario">Limpiar</button>
    </form>

    <!-- Resumen condicional -->
    <div v-if="mostrar && nombre && correo && edad" class="card mt-4">
      <div class="card-body">
        <h5 class="card-title">Resumen de Registro</h5>
        <p><strong>Nombre:</strong> {{ nombre }}</p>
        <p><strong>Correo:</strong> {{ correo }}</p>
        <p><strong>Edad:</strong> {{ edad }}</p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'RegistroForm',
  data() {
    return {
      nombre: '',
      correo: '',
      edad: '',
      mostrar: false
    };
  },
  methods: {
    mostrarResumen() {
      this.mostrar = true;
    },
    limpiarFormulario() {
      this.nombre = '';
      this.correo = '';
      this.edad = '';
      this.mostrar = false;
    }
  }
};
</script>

<style scoped>
.card {
  background-color: #f8f9fa;
}
</style>
