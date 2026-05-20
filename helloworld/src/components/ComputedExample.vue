<template>
    <div>
        <label v-font-size>Subtotal</label>
        <input type="number" v-model="subtotal">
        <h3 v-custom-size:xxl>Total impuesto a pagar: {{ totalVar }} ({{ vat }}%)</h3>
        <h3 v-custom-font.xxl.blue>Total impuesto a pagar: {{ totalVar }} ({{ vat }}%)</h3>

    </div>
</template>

<script lang="ts" setup>
import {Ref, ref, computed } from 'vue'

const vat = 21
let subtotal:Ref<number> = ref(0)
const totalVar = computed(() => (vat*subtotal.value) / 100)

</script>

<style scoped>

</style>