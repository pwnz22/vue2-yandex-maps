<template>
    <div id="app">
        <yandex-map 
        :center="options.center"
        :markerCoords="options.markerCoords"></yandex-map>
    </div>
</template>

<script>
import YandexMap from './components/YandexMap'
import YandexPlacemark from './components/YandexPlacemark'

export default {
    name: 'app',

    data() {
        return {
            options: {
                center: [55, 37],
                markerCoords: [
                    [55.75, 37.50], 
                    [55.75, 37.71], 
                    [55.70, 37.70],
                    [52, 37.75]
                ]
            }
        }
    },

    components: {
        YandexMap, YandexPlacemark
    }
}
</script>
