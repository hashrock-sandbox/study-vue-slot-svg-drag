<template>
    <g @pointermove="onPointerMove" @pointerdown="onPointerDown" @pointerup="onPointerUp" :transform="transform">
        <slot :x="x" :y="y" :selected="selected"></slot>
    </g>
</template>

<script>
export default {
    data(){
        return {
            x: -1,
            y: -1,
            selected: false,
        }
    },
    computed:{
        transform(){
            return `translate(${this.x},${this.y})`
        }
    },
    methods:{
        onPointerMove(ev){
            if(this.selected){
                this.x = ev.offsetX;
                this.y = ev.offsetY;
                this.$emit("change", {
                    x:this.x,
                    y: this.y
                })
            }
        },
        onPointerDown(ev){
            this.selected = true;
            this.$el.setPointerCapture(ev.pointerId)
        },
        onPointerUp(ev){
            this.selected = false;
        }
    }
}
</script>

<style>

</style>
