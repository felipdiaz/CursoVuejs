<template>
    <p>Directiva IF</p>
    <h1 v-if="age < 18">Eres menor de edad</h1>
    <h1 v-else>Eres mayor de edad</h1>
    <br>
    <p>Directiva SHOW</p>
    <h1 v-show="age < 18">Eres menor de edad</h1>
    <h1 v-show="age >= 18">Eres mayor de edad</h1>
</template>

<script lang="ts" setup>
    let age = 20;
</script>

<style scoped>
</style>