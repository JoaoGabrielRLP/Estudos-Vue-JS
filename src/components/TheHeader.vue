<template>
    <header class="">
        Header
    </header>
</template>

<script>
    export default {
    mounted(){
        window.addEventListener('resize', this.resize)
    },    

    beforeUnmount() {
        //Destruir libs, eventos, listeners
        console.log('Before Unmount');
        window.removeEventListener('resize', this.resize) //Vamos matar o evento para o mesmo não ficar rodando o tempo inteiro
    },
    Unmounted() {
        console.log('Unmouted');
    },

    methods: {
        resize($evt){
            console.log($evt)
        }
    }
    }
</script>

<style>
    header {
        background: #000000;
        color: #fff;
    }
</style>