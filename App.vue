<template>
  <div>
    <svg-canvas v-slot="slotProps">
      <svg-draggable v-slot="drag" @change="onChange">
        <circle fill="white" stroke="black" cx="0" cy="0" :r="10" :selected="drag.selected"></circle>
      </svg-draggable>
    </svg-canvas>

  </div>
</template>
<script>
import MyComp from "./MyComp.vue"
import SvgCanvas from "./SvgCanvas.vue"
import SvgDraggable from "./SvgDraggable.vue"
export default {
  components: {
    MyComp,
    SvgCanvas,
    SvgDraggable
  },
  data() {
    return {};
  },
  methods: {
    onChange(payload){
      console.log(payload)
    }
  }
};
</script>
<style>
.canv{
  border: 1px solid black;
}

circle:selected{
  fill: gray;
}

</style>
