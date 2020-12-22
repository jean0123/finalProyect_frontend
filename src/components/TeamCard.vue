<template>
  <div class="card text-white" style="background-color: #4e5459">
    <div class="d-flex justify-content-center p-2">
      <img :src="member.image" alt="image del integrante" />
    </div>
    <div class="card-body" style="height: 230px">
      <h6 class="card-title">Código: {{ member.codigo }}</h6>
      <h6 class="card-title">Rol: {{ member.rol }}</h6>
      <hr style="background-color: white" />
      <h5 class="card-text">{{ member.nombre }}</h5>
      <p class="card-text">{{ member.descripcion }}</p>
    </div>
  </div>
</template>

<script>
export default {
  name: "TeamCard",
  props: {
    member: Object,
  },
};
</script>

<style scoped>
</style>
