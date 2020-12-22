<template>
  <div>
    <nav class="navbar navbar-expand-lg navbar-dark bg-dark">
      <div class="container-fluid">
        <img
          alt="Vue logo"
          src="../assets/logo.jpg"
          height="45px"
          width="50px"
        />
        <form class="d-flex justify-content-end">
          <button
            class="btn btn-outline-danger"
            type="submit"
            @click.prevent="logOut"
          >
            Salir
          </button>
        </form>
      </div>
    </nav>
    <div class="container">
      <p>{{ user.name }}</p>
      <p>{{ user.email }}</p>
    </div>
  </div>
</template>

<script>
import VueJwtDecode from "vue-jwt-decode";
export default {
  data() {
    return {
      user: {},
    };
  },
  methods: {
    getUserDetails() {
      const autenticado = localStorage.getItem("auth");
      if (autenticado) {
        let token = localStorage.getItem("jwt");
        this.user = VueJwtDecode.decode(token);
        localStorage.setItem("user", JSON.stringify(this.user));
      }
    },
    logOut() {
      localStorage.removeItem("jwt");
      localStorage.removeItem("auth");
      localStorage.removeItem("user");
      this.$router.push("/");
    },
  },
  created() {
    console.log("por lo menos entrpo?");
    this.getUserDetails();
  },
};
</script>

<style>
</style>