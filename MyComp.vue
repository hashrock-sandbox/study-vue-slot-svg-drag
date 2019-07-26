<template>
    <div>
        <h1>Hello, MyComp</h1>
        <p @pointermove="onPointerMove">
            <slot :x="x" :y="y"></slot>
        </p>
    </div>
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
p{
    border: 1px solid yellowgreen;
}
</style>
