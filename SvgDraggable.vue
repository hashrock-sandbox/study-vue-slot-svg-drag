<template>
    <g @pointermove="onPointerMove" @pointerdown="onPointerDown" @pointerup="onPointerUp" :transform="transform">
        <slot :x="x" :y="y" :selected="selected"></slot>
    </g>
</template>

<script>
//座標変換とOffsetを引き剥がしたい
//イベントをシンプルにchangeに置き換えたい

export default {
    props: {
        point: Object
    },
    data(){
        return {
            x: this.point.x,
            y: this.point.y,
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
