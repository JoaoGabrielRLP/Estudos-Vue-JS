<template>
    <div :class="BaseClass"> <!-- Quando o que estiver na classe for verdadeiro, ou seja, se a classe existir, aplique a classe css ao prop variant que é igual a 'sucess', esse 'sucess' está definido no app.vue --> 
        
        <slot />

        <button @click="onClick()">
            X
        </button>
    </div>
</template>

<script>
    export default {
        // São as propriedades que iremos passar do componente pai para o componente filho
        props: {
            variant: {
                type: String,
                default: ''
            },
        },

        computed: {
            BaseClass(){
                return [
                    'alert',
                    this.variant ? `alert-${this.variant}` : ''
                ]
            }
        },

        methods: {
            onClick(){
                this.$emit('close') //Evento personalizado
                console.log('Clicou');
            }
        }
    }
</script>

<style scoped>
    .alert {
        display: flex;
        justify-content: space-between;
        padding: 5px;
        border-radius: 6px;
        color: gray; 
        background: #ddd;
    }

    .alert-success{
        background: #42b983;
        color: #fff;
    }

    .alert-danger {
        background: red;
        color: #fff;
    }
</style>