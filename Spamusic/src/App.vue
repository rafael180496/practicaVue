<template>


    <div id="app" class="container">
      <h1 class="center-align light-blue-text">Platzimusic</h1>

        <select class="browser-default light-blue-text" v-model="selectedCountry">
          <option value="" disabled selected>Seleccione el pais</option>
          <option   v-for="pais in paises" v-bind:value="pais.value">
          {{pais.name}}
          </option>

        </select>
      <spinner v-show="load"></spinner>
      <div class="row" v-show="!load">
            <artist v-for="artist in artists" :artist="artist" :key="artist.mbid">

            </artist>
      </div>

    </div>
</template>

<script>
//importar los componentes personales
import Artist from './components/Artist.vue'
import Spinner from './components/Spinner.vue'
import getArtists from './api'



export default {
  name: 'app',
  data () {
    return {
      artists:[],
      paises:[
        {name:'Argentina',value:'argentina'},
        {name:'Colombia',value:'Colombia'},
        {name:'España',value:'spain'},
        {name:'Nicaragua',value:'nicaragua'},
        {name:'China',value:'china'}
      ],
      selectedCountry:'nicaragua',
      load: true
    }
  },
  //agreagar componentes
  components:{
    Artist:Artist,
    Spinner:Spinner
  },
  //cuando se monta ya el doom
  mounted:function(){
    const self =this//objeto vue
    console.log(this.selectedCountry);
    this.load=true
      getArtists(this.selectedCountry)//then es una promesa que devuelve con un metodo
      .then(function(artists){
        self.load=false
        self.artists=artists
      })
  },
  //cambio al seleccionar
  watch:{
    selectedCountry:function(){
      const self =this//objeto vue
      console.log(this.selectedCountry);
      this.load=true
        getArtists(this.selectedCountry)//then es una promesa que devuelve con un metodo
        .then(function(artists){
          self.load=false
          self.artists=artists
        })
    }
  }
}
</script>
<style>

</style>
