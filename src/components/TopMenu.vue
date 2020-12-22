<template>
  <nav
    class="navbar navbar-expand-lg sticky-top navbar-dark"
    style="background-color: #4e5459"
  >
    <a class="navbar-brand" href="# ">
      <img
        src="../assets/logo.jpg"
        width="150"
        height="70"
        class="d-inline-block align-top"
        style="margin: -10px"
      />
    </a>
    <div class="collapse navbar-collapse justify-content-end" id="navbarNav ">
      <ul class="navbar-nav">
        <li class="nav-item active">
          <a class="nav-link" href="# "
            >Home <span class="sr-only">(current)</span></a
          >
        </li>
        <li class="nav-item">
          <a class="nav-link" href="# ">Services</a>
        </li>
        <li class="nav-item">
          <a class="nav-link" href="# ">News</a>
        </li>
        <li class="nav-item">
          <a class="nav-link" href="# ">Team</a>
        </li>
      </ul>
    </div>
  </nav>
</template>

<script>
export default {
  name: "TopMenu",
};
</script>
