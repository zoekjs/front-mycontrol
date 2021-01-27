<template>
  <div>
    <section
      class="jumbotron text-center fondo"
      :style="{
        backgroundImage: `linear-gradient(rgba(0,0,0,0.5), rgba(0,0,0,0.5)), url(${backgroundUrl})`,
      }"
    >
      <div class="container">
        <div class="container breadcrumb bg-info col-md-4 registro mt-5 d-flex justify-content-center">
          <h1 class="well">Iniciar Sesión</h1>
          <div class="col-lg-12 well">
            <div class="row">
              <div class="col-sm-12">
                <div class="row d-flex flex-direction: column">
                  <div class="col-sm-12 form-group text-left">
                    <label>Correo:</label>
                    <input
                      type="text"
                      placeholder="Ingrese Correo"
                      class="form-control"
                    />
                  </div>
                  <div class="col-sm-12 form-group login text-left">
                    <label>Contraseña:</label>
                    <input
                      type="password"
                      placeholder="Ingrese contraseña"
                      class="form-control"
                    />
                  </div>
                </div>
                <div class="col-sm-12 form-group center login__button">
                  <a class="btn btn-lg btn-secondary boton2 text-white" 
                    >Iniciar sesión
                    <span class="icon-arrow-right"></span>
                  </a>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>
  </div>
</template>

<script>
import backgroundUrl from "../assets/img/fondo.jpeg";
export default {
  name: "Login",
  data() {
    return {
      backgroundUrl,
    };
  },
};
</script>

<style lang="scss">
.fondo {
  background-repeat: no-repeat;
  background-attachment: fixed;
  background-position: center;
  background-size: cover;
  opacity: 1;
  margin: 0;
  min-height: 600px;
  padding-top: 115px;
  .loggin__button{
    display: flex;
    margin-bottom: 10px;
    justify-content: center;
    margin-top: 5px;
    a.btn{
      width: 145px;
    }
  }
}
</style>