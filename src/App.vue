<script setup>
    import Header from './components/header/Header.vue';
    import Main from './components/wrapper/Main.vue';
    import Button from './components/buttons/button.vue'
</script>

<template>
   <Header />
   <Main />
</template>

<style>
    :root{
        --gap: 1.5625rem;
        /* color */
        --ligth-color: #FFFBFC;
        --dark-color: #a0a0a0;
        --grey-color: #ececec2c;
        --red-color: #ffdde77d;
        /* font color */
        --black-font: #1d1d1d; 
        --grey-font: #BABABA;
        --grey-card-font: #979797;
        /* shadow */
        --card-shadow: 5px 5px 12px 1px rgba(133,133,133,0.68);
    }
</style>
