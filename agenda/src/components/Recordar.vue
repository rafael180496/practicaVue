<template lang="html">
  <div id="record">
    <div class="container">

      <div class="row">
        <div v-show="load" class="col">
            <br>
            <br>
            <br>
            <br>
            <h1 class="text-center text-primary">Ingrese Recordatorio</h1>
            <h3 class="text-center text-secondary">Toque el boton AGREGAR para ingresar uno nuevo.</h3>
        </div>
      </div>
      <div class="row">
        <div v-show="!load" >
          <div class="col-sm-4">
            <div class="card" >
              <div class="card-body">
                <h5 class="card-title">Card title</h5>
                <h6 class="card-subtitle mb-2 text-muted">Card subtitle</h6>
                <p class="card-text">Some quick example text to build on the card title and make up the bulk of the card's content.</p>
                <a href="#" class="card-link">Card link</a>
                <a href="#" class="card-link">Another link</a>
              </div>
            </div>
          </div>
          <div class="col-sm-4">
            <div class="card" >
              <div class="card-body">
                <h5 class="card-title">Card title</h5>
                <h6 class="card-subtitle mb-2 text-muted">Card subtitle</h6>
                <p class="card-text">Some quick example text to build on the card title and make up the bulk of the card's content.</p>
                <a href="#" class="card-link">Card link</a>
                <a href="#" class="card-link">Another link</a>
              </div>
            </div>
          </div>
        </div>
      </div>
      <div class="row">
          <template v-if="agre">
            <button type="button" class="agregar btn btn-dark btn-lg btn-block">Agregar Recordatorio</button>
          </template>
      </div>

    </div>


  </div>

</template>

<script>
export default {
  name: 'record',
  data () {
    return {
      card:[],
      load: false,
      agre:true
    }
  }
}
</script>

<style lang="css">
.agregar{
  position:absolute;
   bottom:1px;
   right:0px;
   left:0px;

}
</style>
