<template>
  <div class="container mt-5">
    <form>
      <div class="mb-3">
        <label for="exampleInputEmail1" class="form-label">Email address</label>
        <input
          v-model="login.email"
          type="email"
          class="form-control"
          id="exampleInputEmail1"
          aria-describedby="emailHelp"
        />
        <div id="emailHelp" class="form-text">
          We'll never share your email with anyone else.
        </div>
      </div>
      <div class="mb-3">
        <label for="exampleInputPassword1" class="form-label">Password</label>
        <input
          v-model="login.password"
          type="password"
          class="form-control"
          id="exampleInputPassword1"
        />
      </div>
      <button type="submit" class="btn btn-primary" @click.prevent="loginUser">
        Submit
      </button>
    </form>
  </div>
</template>

<script>
import swal from "sweetalert";
export default {
  name: "TheLogin",
  data() {
    return {
      login: {
        email: "",
        password: "",
      },
    };
  },
  methods: {
    async loginUser() {
      try {
        let response = await this.$http.post("/api/auth/signin", this.login);
        if (response.data.accessToken) {
          localStorage.setItem("jwt", response.data.accessToken);
          localStorage.setItem("auth", response.data.auth);
          swal("Perfecto!", "Login correcto", "success");
          this.$router.push("/home");
        }
      } catch {
        swal("Opps!", "Algo salió mal", "error");
      }
    },
  },
};
</script>

<style>
</style>