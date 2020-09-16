<template>
  <div id="mapid"></div>
</template>

<script>
import 'leaflet/dist/leaflet';
import 'leaflet/dist/leaflet.css';



export default {
  name: "mapa",
  data: function() {
    return {
      mymap: null,
      latitud: null,
      longitud: null
    }
  },
  /*mounted: function(){
    let _this = this;
    this.mymap = L.map('mapid').setView([-38.719, -72.478], 7);

    L.tileLayer('http://{s}.tile.osm.org/{z}/{x}/{y}.png', {
      attribution: '&copy; <a href="http://osm.org/copyright">OpenStreetMap</a> contributors',
      maxZoom: 10
    }).addTo(this.mymap);

    this.mymap.on('click', function(e){
      _this.latitud = e.latlng.lat;
      _this.longitud = e.latlng.lng;
    })
  }*/
  /*created: () => ({

    var marker = L.marker([-51.760928, -72.482996]).addTo(mymap);

    var circle = L.circle([-34.1708, -70.7444], {
      color: 'red',
      fillColor: '#ff0033',
      fillOpacity: 0.5,
      radius: 15000
    }).addTo(mymap);
}),*/



  /*
  var circle = L.circle([-34.1708, -70.7444], {
    color: 'red',
    fillColor: '#f03',
    fillOpacity: 0.5,
    radius: 15000
  }).addTo(mymap);
  */

}


</script>

<style scoped>
#mapid {
  height: 400px;
  /*  width:200px;*/
}
</style>