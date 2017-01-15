<template>
    <div class="yandex-placemark"></div>
</template>

<script>
    export default {
        name: 'yandex-placemark',

        props: ['markers'],

        methods: {
            placemark() {

                const myCollection = new ymaps.GeoObjectCollection(null, {
                    preset: 'islands#redIcon', //все метки красные
                    draggable: false
                })

                for (var i = 0; i < this.markers.length; i++) {
                    myCollection.add(new ymaps.Placemark(this.markers[i]))
                }

                myMap.geoObjects.add(myCollection)
            }
        },

        created() {
            this.placemark()
        }

    }
</script>
