<template>
      <header class="">
        <h1 
        v-if="$slots.title"
        class="title">
            <slot name="title" />
        </h1>
        
        <div class="description">
            <slot name="description" />
        </div>
       
        <div class="content">
            <slot />
        </div>
        
    </header>
</template>

<script>
    export default {
        mounted(){
            console.log(this.$slots) //Aqui temos a lista com todos os slots disponíveis do componente
        }
    }
</script>

<style>
    header {
        background: #000000;
        color: #fff;
    }
</style>