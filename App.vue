<template>
  <div>
    <svg-canvas v-slot="slotProps">
      <g>
        <line
          stroke="black"
          :x1="points[0].x"
          :y1="points[0].y"
          :x2="points[1].x"
          :y2="points[1].y"
        />
      </g>
      <svg-draggable
        v-for="(point, idx) in points"
        :key="idx"
        v-slot="drag"
        :point="point"
        @change="updatePoint(point, $event)"
      >
        <circle fill="white" stroke="black" cx="0" cy="0" :r="10" :selected="drag.selected"></circle>
      </svg-draggable>
    </svg-canvas>

    <div>
      <div v-for="(p, idx) in points" :key="idx">{{p.x}} {{p.y}}</div>
    </div>
  </div>
</template>
<script>
import MyComp from "./MyComp.vue";
import SvgCanvas from "./SvgCanvas.vue";
import SvgDraggable from "./SvgDraggable.vue";
export default {
  components: {
    MyComp,
    SvgCanvas,
    SvgDraggable
  },
  data() {
    return {
      points: [{ x: 100, y: 100 }, { x: 200, y: 200 }]
    };
  },
  methods: {
    onChange(payload) {
      console.log(payload);
    },
    updatePoint(obj, payload) {
      // console.log(obj, payload)
      obj.x = payload.x;
      obj.y = payload.y;
    }
  }
};
</script>
<style>
.canv {
  border: 1px solid black;
}

circle:selected {
  fill: gray;
}
</style>
