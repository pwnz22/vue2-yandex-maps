<template>
    <div>
        <div id="map"></div>
    </div>
</template>

<script>
export default {
   name: 'yandex-map',
   
   props: ['markerCoords', 'center'], 

   methods: {
        init() {
            const map = new ymaps.Map('map', {
                center: [52, 37.75],
                zoom: 7
            }, {
                searchControlProvider: 'yandex#search' 
            }),

            markerCollection = new ymaps.GeoObjectCollection(null, {
                preset: 'islands#blueIcon'
            }),

            markerCoords = this.markerCoords

            for (let i = 0; i < markerCoords.length; i++) {
                markerCollection.add(new ymaps.Placemark(markerCoords[i]))
            }

            map.geoObjects.add(markerCollection)

        },

        mapInit() {
            ymaps.ready(this.init)
        }
    },

    mounted() {
        this.mapInit()
    }
}
</script>

<style>
    #map {
        width: 600px;
        height: 400px;
    }
</style>
