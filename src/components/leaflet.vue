<template>
    <div id="mapContainer" style="width:40vw; height: 40vh"></div>
</template>

<script>
import L from "leaflet";

export default {
    data(){
        return {
            center: [48.78559445620188, 2.4353308306852246]
        }
    },
    methods: {
   setupLeafletMap: function () {
     const mapDiv = L.map("mapContainer").setView(this.center, 15);
     L.tileLayer(
       "http://openmapsurfer.uni-hd.de/tiles/roads/x={x}&y={y}&z={z}",
       {
         attribution:
           '<a href="https://www.lije-creative.com">LIJE Creative</a>',
         maxZoom: 18,
       }
     ).addTo(mapDiv);
    const circle = L.circle(this.center, {
                                color: 'red',
                                fillColor: '#f03',
                                fillOpacity: 0.5,
                                radius: 20
                            }).addTo(mapDiv);
        circle.bindPopup("Afpa, 9 Rue Marc Seguin, 94015 Créteil").openPopup();
   },
 },
    mounted(){
        this.setupLeafletMap();
    }
}
</script>

<style>

</style>