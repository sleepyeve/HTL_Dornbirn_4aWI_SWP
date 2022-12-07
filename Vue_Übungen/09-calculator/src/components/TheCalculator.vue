<template>
    <section>
        <h1>Simple Calculator</h1>
        <input type="text" ref="diplayText" v-model="this.inputText">
        <div>
            <simple-button @button-clicked="operator" :buttonName="'+'"></simple-button>
            <simple-button @button-clicked="operator" :buttonName="'-'"></simple-button>
            <simple-button @button-clicked="operator" :buttonName="'*'"></simple-button>
            <simple-button @button-clicked="operator" :buttonName="'/'"></simple-button>
        </div>
        <button class="resultButton" @click="calculate">=</button>
    </section>
</template>

<script>
import SimpleButton from './SimpleButton.vue'

export default {
    components: {
        SimpleButton,
    },
    data() {
        return{
            inputText: "",
        }
    },
    methods: {
        operator(buttonName){
            this.inputText = this.inputText + " " + buttonName + " ";
            this.$refs.displayText.focus();
        },
        calculate(){
            this.inputText = eval(this.inputText);
            this.$refs.displayText.focus();
        }
    },
    
}
</script>

<style>
    section {
        display:flex;
        flex-direction:column;
        width:30vw;
        background-color: #d1f4f2;
        justify-content: space-evenly;
        margin: auto;
        align-items: center;
        padding-bottom: 10pt;
    }
    input{
        margin-bottom: 10pt;
        width: 90%;
    }
    div{
        display: grid;
        grid-template-columns: 25% 25% 25% 25%;
        width: 90%;
    }
    .resultButton {
        width: 90%;
    }
</style>