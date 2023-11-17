<template>
    <div class="mt-4">
      <strong>Resultado:</strong> {{ resultado }}
    </div>
  </template>
  
  <script>
  export default {
    props: {
      resultado: Number,
    },
  };
  </script>
  