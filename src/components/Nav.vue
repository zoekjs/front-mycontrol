<template>
  <nav class="navbar navbar-expand-lg navbar-dark bg-dark">
    <div class="container">
      <h4 class="text-light">My Control</h4>
      <div
        class="collapse navbar-collapse justify-content-end"
        id="navbarsExampleDefault"
      >
        <ul class="navbar-nav m-auto">
          <li class="nav-item">
            <a class="nav-link" a href="#sobrenosotros" @click="alerta">Sobre Nosotros</a>
          </li>
          <li class="nav-item">
            <a class="nav-link" href="/"><span class="icon-home"></span></a>
          </li>

          <li class="nav-item">
            <a class="nav-link" a href="#contactenos">Contáctenos</a>
          </li>
        </ul>
      </div>
      <div>
        <router-link :to="{ name: 'login'}"><a class="btn btn-success btn-m ml-3 text-white">
          Iniciar Sesión <span class="icon-user-o"></span>
          <span class="badge badge-light"></span>
        </a>
        </router-link>
      </div>
    </div>
  </nav>
</template>

<script>

export default {
  name: "navBar",
  methods: {
    alerta() {
      this.$swal('Hello Vue world!!!');
    }
  }
};
</script>