<template>
<p v-bind:class="{'danger': hasError}">El mensaje se ha enviado satisfactoriamente.</p>
<p v-bind:style="{backgroundColor: '#ccc', 'font-size': ' 15px', color: c}">El mensaje esta en otro color</p>
<button v-on:click="handleClick()">Cambiar color</button>
</template>

<script lang="ts" setup>
import {ref} from 'vue'; 
    let c = ref('#fff');
    let hasError = false;
    const handleClick = () => {c.value = '#ff000'}

</script>

<style>
.danger {
    color: red;
}
</style>