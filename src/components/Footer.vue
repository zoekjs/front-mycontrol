<template>
  <div>
    <footer class="text-light bg-dark">
      <div class="container">
        <div class="row">
          <div class="col-lg-3 col-lg-4 col-xl-3">
            <a name="sobrenosotros">
              <h5>Sobre Nosotros</h5>
            </a>
            <hr class="bg-white mb-2 mt-0 d-inline-block mx-auto w-25" />
            <p class="mb-0 text-justify">
              My control nos permite un manejo optimizado de la información,
              junto con el control de los datos de personas, tanto en edificios
              residenciales como coorporativos.
            </p>
          </div>

          <div class="col-lg-3 col-lg-2 col-xl-2 mx-auto">

          </div>

          <div class="col-lg-4 col-lg-3 col-xl-3">
            <a name="contactenos">
              <h5>Contáctenos</h5>
            </a>
            <hr class="bg-white mb-2 mt-0 d-inline-block mx-auto w-25" />
            <ul class="list-unstyled">
              <li><i class="fa fa-home mr-2"></i> Mycontrol en Slack</li>
              <li>
                <i class="fa fa-envelope mr-2 mt-3"></i> contacto@mycontrol.cl
              </li>
              <li><i class="fa fa-phone mr-2 mt-3"></i> +56223373568</li>
            </ul>
          </div>

          <div class="col-12 copyright mt-3">
            <p>
              <a href="#">Volver arriba</a>
            </p>
            <p class="text-right">
              desastre arreglado <i class="fa fa-heart"></i> por
              <a><i>EL GRAN ZOEK</i></a>
            </p>
          </div>
        </div>
      </div>
    </footer>
  </div>
</template>

<script>
export default {
  name: 'Footer'
}
</script>

<style lang="scss">
  footer{
    padding-top: 50px;
  }
</style>