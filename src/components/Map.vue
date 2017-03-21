<template>
  <gmap-map
    :center="center"
    :zoom="4"
    style="width: 100%px; height: 300px"
  >
    <gmap-marker
      v-for="m in markers"
      :position="m.position"
      :clickable="true"
      :draggable="true"
      @click="center=m.position"
    ></gmap-marker>
  </gmap-map>
</template>

<script>
  import * as VueGoogleMaps from 'vue2-google-maps'
  import Vue from 'vue'

  Vue.use(VueGoogleMaps, {
    load: {
      key: 'AIzaSyDGZlmy2nLNwpx-QESqRVogO4Utg7h46LE ',
      v: 'OPTIONAL VERSION NUMBER'
    }
  })

  export default {
    data () {
      return {
        center: {lat: 22.4178481, lng: 114.2093172},
        markers: [{
          position: {lat: 22.4178481, lng: 114.2093172}
        }, {
          position: {lat: 11.0, lng: 15.0}
        }]
      }
    }
  }
</script>
