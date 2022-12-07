<template>
    <button @click="buttonClicked">{{buttonName}}</button>
</template>

<script>

export default {
    
    emits:['button-clicked'],

    props:{
        buttonName: {
            type: String,
            required: true,
        }
    },
    methods: {
        buttonClicked() {
            this.$emit('button-clicked', this.buttonName);
        }
    }
};
</script>

<style>
    button {
        background-color: rgb(63, 249, 212);
        color:black;
        padding: 10px 35px;
        border: solid black 1px;
        font-weight: bold;
    }
    button:hover{
        background-color:#a2a2d0;
        color: white;
    }
</style>