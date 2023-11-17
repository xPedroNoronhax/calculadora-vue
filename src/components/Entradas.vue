<template>
    <div class="row">
      <div class="col-md-4">
        <label :for="id">{{ label }}:</label>
        <input :id="id" :value="valor" type="number" class="form-control" @input="atualizar">
      </div>
    </div>
  </template>
  
  <script>
  export default {
    props: {
      id: String,
      label: String,
      valor: Number,
    },
    methods: {
      atualizar(event) {
        this.$emit('atualizar', event.target.value);
      },
    },
  };
  </script>
  