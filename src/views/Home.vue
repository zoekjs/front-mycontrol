<template>
  <div
    class="home"
    :style="{
      backgroundImage: `linear-gradient(rgba(0,0,0,0.5), rgba(0,0,0,0.5)), url(${backgroundUrl})`,
    }"
  >
    <div class="container text-center amigable mb-5">
      <img alt="logo" id="logo" class="img-fluid" src="@/assets/img/logo.png" />
      <h1 class="jumbotron-heading text-white">
        | Amigable | Eficiente | Seguro |
      </h1>
    </div>
    <div class="container">
      <div class="row">
        <div class="col">
          <nav aria-label="breadcrumb">
            <ol class="breadcrumb">
              <li class="breadcrumb-item"><a href="/">Inicio</a></li>
              <li class="breadcrumb-item active" aria-current="page">
                Registrarse
              </li>
            </ol>
          </nav>
        </div>
      </div>
    </div>
    <div class="container">
      <div class="container breadcrumb bg-info registro">
        <h1 class="well">Registrarse</h1>
        <div class="col-lg-12 col-lg-6 well">
          <div class="row">
            <form class="col-sm-12" id="form-usuarios">
              <div class="col-sm-12">
                <div class="row">
                  <div class="col-sm-12 col-lg-6 orm-group">
                    <label>Correo:</label>
                    <input
                      type="email"
                      placeholder="Ingrese Correo"
                      class="form-control"
                      name="email"
                      v-model="email"
                    />
                  </div>
                  <div class="col-sm-12 col-lg-6 form-group">
                    <label>Contraseña:</label>
                    <input
                      type="password"
                      placeholder="Ingrese contraseña"
                      class="form-control"
                      name="password"
                      v-model="password"
                    />
                  </div>
                </div>
                <div class="row">
                  <div class="col-sm-12 col-lg-6 form-group">
                    <label>Nombre Edificio:</label>
                    <input
                      type="text"
                      placeholder="Nombre edificio"
                      class="form-control"
                      v-model="nombreEdificio"
                    />
                  </div>
                  <div class="col-sm-12 col-lg-6 form-group">
                    <label path="confirmPassword">Confirmar Contraseña:</label>
                    <input
                      type="password"
                      placeholder="Confirme su contraseña"
                      class="form-control"
                      v-model="confirmPassword"
                    />
                  </div>
                </div>
                <div class="row">
                  <div class="col-sm-12 col-lg-6 form-group">
                    <label>Rut:</label>
                    <input
                      type="text"
                      placeholder="Ingrese su Rut"
                      class="form-control"
                      v-model="rut"
                    />
                  </div>
                  <div class="col-sm-12 col-lg-6 form-group">
                    <label>Direccion:</label>
                    <input
                      type="text"
                      placeholder="Ingrese su dirección"
                      class="form-control"
                      v-model="direccion"
                    />
                  </div>
                </div>
                <div class="row row__buttons">
                  <div class="col-sm-12 form-group">
                    <h5>¿Ya tienes cuenta?</h5>
                  </div>
                  <div class="col-sm-12 login__buttons">
                    <router-link :to="{ name: 'login' }"
                      ><a class="btn btn-lg btn-secondary cuenta text-white"
                        >Iniciar Sesión
                        <span class="icon-arrow-right"></span>
                      </a>
                    </router-link>
                    <a class="btn btn-lg btn-secondary" @click="usuario()"
                      >Vamos
                      <span class="icon-arrow-right"></span>
                    </a>
                  </div>
                </div>
              </div>
            </form>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>


<script>
// @ is an alias to /src
import backgroundUrl from "../assets/img/fondo.jpeg";
import axios from "axios";
export default {
  name: "home",
  data() {
    return {
      backgroundUrl,
      email: "",
      nombreEdificio: "",
      password: "",
      confirmPassword: "",
      rut: "",
      direccion: "",
    };
  },
  methods: {
    usuario() {
      const usuario = {
        email: this.email,
        nombreEdificio: this.nombreEdificio,
        password: this.password,
        rut: this.rut,
      };
      if (
        this.email == "" ||
        this.email == null ||
        this.nombreEdificio == '' ||
        this.nombreEdificio == null ||
        this.password == "" ||
        this.password == null
      ) {
        this.$swal("Error", "Debe llenar todos los campos", "error");
      } else {
        if (this.password != this.confirmPassword) {
          this.$swal("Error", "Las contraseñas no coinciden", "error");
        } else {
          console.log(usuario)
          axios
            .post("http://localhost:8080/api/usuarios", usuario)
            .then((res) => {
              this.$swal(
                "Felicidades",
                "El usuario fue creado correctamente :)",
                "success"
              );
              console.log(res);
            })
            .catch((err) => console.log(err));
          document.getElementById("form-usuarios").reset();
        }
      }
    },
  },
};
</script>

<style lang="scss">
.home {
  background-repeat: no-repeat;
  background-attachment: fixed;
  background-position: center;
  background-size: cover;
  opacity: 1;
  min-height: 1000px;
  div.row.row__buttons {
    .login__buttons {
      display: flex;
      justify-content: space-between;
      flex-wrap: wrap;
    }
  }
}
</style>