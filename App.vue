<template>
  <div>
    <my-comp v-slot="slotProps">
      This is Slot! ({{slotProps.x}},{{slotProps.y}})
    </my-comp>

    <svg class="canv" width=400 height=400 viewBox="0 0 400 400">
      <rect x=0 y=0 width=10 height=10>
    </svg>
  </div>
</template>
<script>
import MyComp from "./MyComp.vue"
export default {
  components: {
    MyComp
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
