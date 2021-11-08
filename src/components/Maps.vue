<template>
  <div id="map" style="width:100%; height: 80vh"></div>
</template>

<script>
import { Loader } from '@googlemaps/js-api-loader';
export default {
    mounted(){
        const loader = new Loader({
        apiKey: "Key goes here",
        version: "weekly",
        libraries: ["places"]
        });
        const mapOptions = {
        center: {
            lat: 48.7855661801919, 
            lng: 2.4355024920556727
        },
        zoom: 18
        };
        loader
            .load()
            .then((google) => {
               const map = new google.maps.Map(document.getElementById("map"), mapOptions);
                const mark =  {
                        lat: 48.7855661801919, 
                        lng: 2.4355024920556727
                    }
                new google.maps.Marker({
                    position: mark,
                    map,
                    title: "Hello World!",
                });
            })
            
    }
}
</script>

<style>

</style>