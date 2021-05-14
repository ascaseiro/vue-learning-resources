<template>
  <base-card>
    <form @submit.prevent="submitData">
      <div class="form-control">
        <label for="titulo">Título</label>
        <input type="text" name="titulo" id="titulo" ref="tituloInput" />
      </div>
      <div class="form-control">
        <label for="descripcion">Descripción</label>
        <textarea
          name="descripcion"
          id="descripcion"
          rows="3"
          ref="descInput"
        ></textarea>
      </div>
      <div class="form-control">
        <label for="link">Link</label>
        <input type="url" name="link" id="link" ref="linkInput" />
      </div>
      <div>
        <base-button type="submit">Guardar recurso</base-button>
      </div>
    </form>
  </base-card>
</template>

<script>
export default {
  inject: ['addResource'],
  methods: {
    submitData() {
      const enteredTitulo = this.$refs.tituloInput.value;
      const enteredDescripcion = this.$refs.descInput.value;
      const enteredLink = this.$refs.linkInput.value;

      this.addResource(enteredTitulo, enteredDescripcion, enteredLink);
    },
  },
};
</script>

<style scoped>
label {
  font-weight: bold;
  display: block;
  margin-bottom: 0.5rem;
}

input,
textarea {
  display: block;
  width: 100%;
  font: inherit;
  padding: 0.15rem;
  border: 1px solid #ccc;
}

input:focus,
textarea:focus {
  outline: none;
  border-color: #3a0061;
  background-color: #f7ebff;
}

.form-control {
  margin: 1rem 0;
}
</style>