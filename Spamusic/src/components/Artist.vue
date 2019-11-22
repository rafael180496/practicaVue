<template lang="html">
  <div id="artist" class="col s12 m6 l3 ">
    <div class="card hoverable z-depth-1">
        <div class="card-image">
                <img :src="artist.image[3]['#text']" >
                <span class="card-title">{{artist.name}}</span>
                 <a :href="artist.url"  target="_blank" class="btn-floating halfway-fab waves-effect waves-light blue"><i class="material-icons">add</i></a>
        </div>
    </div>
  </div>
</template>
<script>
export default {
  //nombre de etiqueta
  name:'artist',
  props:['artist']
}
</script>
<style lang="css">

</style>
