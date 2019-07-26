<template>
  <div>
    <my-comp v-slot="slotProps">
      This is Slot! ({{slotProps.x}},{{slotProps.y}})
    </my-comp>

    <svg-canvas v-slot="slotProps">
      <rect :x="slotProps.x" :y="slotProps.y" width=10 height=10>
    </svg-canvas>

  </div>
</template>
<script>
import MyComp from "./MyComp.vue"
import SvgCanvas from "./SvgCanvas.vue"
export default {
  components: {
    MyComp,
    SvgCanvas
  },
  data() {
    return {};
  }
};
</script>
<style>
.canv{
  border: 1px solid black;
}

</style>
