<template>
    <button @click="onClick()" :style={background:color}>{{ text }}</button>
</template>

<script>
    export default {
        name : "Button",
        props: ['text','color'],
        methods:{
            onClick(){
                console.log("button click");
            }
        }
    }
</script>