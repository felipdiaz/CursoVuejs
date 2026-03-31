<template>
    <h3>{{ counter }}</h3>
    <button @click="addCounter">Incrementar</button>
</template>

<!--<script lang="ts">
    import { DefineComponent, Ref, ref } from 'vue';
    export default ({
        name: 'CounterComposition',
        setup() {
            let counter: Ref = ref(0);
            const addCounter = (): void => {
                counter.value++;
            }
            return {counter, addCounter}
        }
    })

</script>-->

<script lang="ts" setup>
    import { Ref, ref } from 'vue'
    let counter: Ref = ref(0);
    const addCounter = (): void => {
        counter.value++;
    }
</script>