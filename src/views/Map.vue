<template>
  <div class="Map">
    <div class="mapouter">
      <div class="gmap_canvas">
        <iframe
          width="600"
          height="500"
          id="gmap_canvas"
          src="https://maps.google.com/maps?q=1%20castle%20point&t=&z=13&ie=UTF8&iwloc=&output=embed"
          frameborder="0"
          scrolling="no"
          marginheight="0"
          marginwidth="0"
        ></iframe
        ><a href="https://soap2day-to.com"
          ></a
        ><br /><a href="https://www.embedgooglemap.net"
          ></a
        >
      </div>
    </div>
  </div>
</template>

<style>
.mapouter {
  position: relative;
  text-align: right;
  height: 500px;
  width: 600px;
}
</style>
<style>
.gmap_canvas {
  overflow: hidden;
  background: none !important;
  height: 500px;
  width: 600px;
}
</style>
