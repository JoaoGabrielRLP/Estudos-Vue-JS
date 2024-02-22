<template>
    <div>
        {{ $route.query.page }}
        Usuários <br>

        <button @click="login()">
            Login
        </button>
    </div>
</template>

<script>
    export default {
        created() {
            //console.log(this.$route); - tem os dados da rota atual
            console.log(this.$router); // Tem funcionalidades do esquema de roteamento
        },
        methods: {
            login(){
                this.$router.push('/about')
                console.log('Chegou')
            }
        }
    }
</script>