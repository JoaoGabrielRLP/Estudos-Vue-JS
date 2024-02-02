<template>
    <div :class="BaseClass"> <!-- Quando o que estiver na classe for verdadeiro, ou seja, se a classe existir, aplique a classe css ao prop variant que é igual a 'sucess', esse 'sucess' está definido no app.vue -->

    <!-- Estamos injetando a variant na class -->
    {{ test }}
    <slot />
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
            test: {
                type: String,
                default: 'test'
            }
        },

        computed: {
            BaseClass(){
                return [
                    'alert',
                    this.variant ? `alert-${this.variant}` : ''
                ]
            }
        }
    }
</script>

<style scoped>
    .alert {
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