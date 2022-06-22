<template>
  <div class="container">
    <div id="peta" class="mt-5" style="height:600px"></div>
    <div class="bg-light py-3 mt-3 fw-bold text-secondary px-3 border border-warning">Panel</div>
  </div>
</template>
<script>
/* eslint-disable no-undef */
export default {
  name: 'About',
  mounted() {
    this.initMap();
  },
  methods: {
    initMap() {
      const map = new google.maps.Map(document.getElementById('peta'), {
        center: { lat: -3.275407, lng:116.197635 },
        zoom: 13,
        mapTypeId: 'terrain'
      })

      const Coordinates = [
        { lat: -3.2682639, lng: 116.2014774 },
        // { lat: -3.26055, lng: 116.21942 },
        // { lat: -3.2683069, lng: 116.218987 },
        { lat: -3.2521342, lng: 116.2138666 },
      ]

      const linePath = new google.maps.Polyline({
        path: Coordinates,
        geodesic: true,
        strokeColor: "#FF0000",
        strokeOpacity: 1.0,
        strokeWeight: 2,
      })

      linePath.setMap(map)
    }
  }
}
</script>