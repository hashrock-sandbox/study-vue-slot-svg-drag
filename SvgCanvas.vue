<template>
    <svg class="canv" width=400 height=400 viewBox="0 0 400 400" @pointermove="onPointerMove">
        <slot :x="x" :y="y"></slot>
    </svg>
</template>

<script>
export default {
    data(){
        return {
            x: -1,
            y: -1
        }
    },
    methods:{
        onPointerMove(ev){
            this.x = ev.offsetX;
            this.y = ev.offsetY;
        }
    }
}
</script>

<style>

</style>
