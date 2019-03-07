<template>
  <section class='home_mg office-map'>
    <div class='grid grid--gut12'>

      <div class='col col--5 offices home_pd'>
        <h1 class='h1_home'>Our Offices</h1>
        <section>
          <h2>London home</h2>
          <p>Bermondsey Studios<br/>3 Morocco Street<br/>London, SE1 3HB</p>
        </section>
        <section>
          <h2>Carribean home</h2>
          <p>Republique Dominicaine<br/>Av Refineria 30<br/>Bajos de Haina 91000<br/>Dominican Republic</p>
        </section>
      </div>

      <div id='map' class='col col--7'></div>

    </div>
  </section>
</template>

<script>
export default {
  name: 'OfficeMap',
  mounted() {
    const mapboxgl = require('mapbox-gl/dist/mapbox-gl.js');

    mapboxgl.accessToken = 'pk.eyJ1IjoidGFkYW4xMjciLCJhIjoiY2pzeWJvb3EzMGFmYTQzcm5qa2I1OWVocCJ9.i-ANlp_wbow8zyK7L1MMRQ';

    const map = new mapboxgl.Map({
      container: 'map',
      style: 'mapbox://styles/mapbox/light-v9',
      zoom: 5,
      center: [3.0, 52.372]
    });
  }
}
</script>

<style lang='less' scoped>
  .office-map {
    padding: 8em 0.8em;

    .offices {
      text-align: left;

      h1 {
        margin-top: 0.1em;
        margin-left: 0;
        padding-bottom: 0.2em;
      }

      section {
        padding-bottom: 1em;
        margin-bottom: 4em;
        h2 {
         font-family: 'Karma SemiBold';
         font-size: 23px;
         margin-bottom: 1em;
        }

        p {
          font-size: 16px;
        }
      }
    }

    #map {
      width: 800px;
      height: 480px;
    }
  }

</style>

<style>
  .mapboxgl-canvas {
    position: relative !important;
  }
  .mapboxgl-ctrl-logo {
    margin-left: 8px !important;
  }
</style>
