<template>
    <div class="Stations">
        <ul>
          <li v-for="station in stations">{{ station.name }}</li>
        </ul>
    </div>
</template>

<script>
    export default {
        data () {
            return {
              stations: []
            }
        },

        ready () {
          this.getStations();
        },

        methods: {
          getStations () {
            this.$http.get('http://apis.is/petrol').then((response) => {
              this.stations = response.data.results;
            });
          }
        }
    }
</script>

<style lang="stylus">

    /*
     * Variables
     */
    color-phonegap = #2fa0c3
    color-vue = #42b983
    color-muted = #CCCCCC


    .Stations
      overflow-x: scroll;

</style>
