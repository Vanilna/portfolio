<template>
  <svg
    xmlns="http://www.w3.org/2000/svg"
    preserveAspectRatio="none"
    version="1.1"
    shape-rendering="geometricPrecision"
    text-rendering="geometricPrecision"
    image-rendering="optimizeQuality"
    fill-rule="evenodd"
    clip-rule="evenodd"
    viewBox="0 0 343 1336.52"
    xmlns:xlink="http://www.w3.org/1999/xlink"
    @click="$emit('arrowClick')"
  >
    <g id="Layer_x0020_1">
      <polyline
        fill="none"
        :stroke="color"
        stroke-width="15"
        stroke-miterlimit="22.9256"
        points="333.69,7.13 4.9,664.7 333.69,1322.27 "
      />
    </g>
  </svg>
</template>
<script>
export default {
  name: "Arrow",
  props: {
    isDisabled: Boolean
  },
  computed: {
    color: function() {
      return this.isDisabled ? "#aaaaaa" : "#ffd500";
    }
  }
};
</script>
