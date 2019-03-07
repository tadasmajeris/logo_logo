<template>
  <section class='home_mg office-map'>
    <div class='grid grid--gut12'>

      <div class='col col--12 col--5-mm offices home_pd'>
        <h1 class='h1_home'>Our Offices</h1>
        <section>
          <h2>
            London home
            <MapMarker color='#994ADF'/>
          </h2>
          <p>Bermondsey Studios<br/>3 Morocco Street<br/>London, SE1 3HB</p>
        </section>
        <section>
          <h2>
            Carribean home
            <MapMarker color='#F1C00A'/>
          </h2>
          <p>Republique Dominicaine<br/>Av Refineria 30<br/>Bajos de Haina 91000<br/>Dominican Republic</p>
        </section>
      </div>

      <div id='map' class='col col--12 col--7-mm'></div>

    </div>
  </section>
</template>

<script>
import MapMarker from './MapMarker';

export default {
  name: 'OfficeMap',
  components: {
    MapMarker
  },
  mounted() {
    const mapboxgl = require('mapbox-gl/dist/mapbox-gl.js');

    mapboxgl.accessToken = 'pk.eyJ1IjoidGFkYW4xMjciLCJhIjoiY2pzeWJvb3EzMGFmYTQzcm5qa2I1OWVocCJ9.i-ANlp_wbow8zyK7L1MMRQ';

    const map = new mapboxgl.Map({
      container: 'map',
      style: 'mapbox://styles/mapbox/light-v9',
      zoom: 1.75,
      center: [-32, 39.7]
    });

    const markerLondon = new mapboxgl.Marker({color: '#994ADF'})
      .setLngLat([-0.0822466, 51.5002244])
      .addTo(map);

    const markerCarribean = new mapboxgl.Marker({color: '#F1C00A'})
      .setLngLat([-70.0373813, 18.4026825])
      .addTo(map);
  }
}
</script>

<style lang='less' scoped>
  @mobile:   ~"only screen and (max-width: 640px)";

  .office-map {
    padding: 8em 0.8em;

    .offices {
      text-align: left;
      padding-right: 1em !important;

      h1 {
        margin: 0;
        padding-bottom: 1.1em;
        line-height: 0.9;
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

    @media @mobile {
      padding-top: 2em;

      .offices {
        text-align: center;
        section {
          padding-bottom: 0 !important;
        }
      }

      #map {
        height: 300px;
        padding-left: 0;
      }

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
