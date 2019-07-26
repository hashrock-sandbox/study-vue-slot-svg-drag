<template>
  <div>
    <my-comp v-slot="slotProps">
      This is Slot! ({{slotProps.x}},{{slotProps.y}})
    </my-comp>
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