<template>
    <div class="container d-flex justify-content-center mt-4 mb-2">
        <div v-html="`Found ${store.characterList.length} characters`" class="found fw-bold"></div>
    </div>
</template>

<script>
import { store } from '../store';
    export default {
        name: 'CounterComponent',
    data() {
        return {
            store,
        }
    },
    }
</script>

<style lang="scss" scoped>
@use '../assets/style/partials/variables' as*;
.found {
    background-color: $bg-barra;
    color: $text-white;
    width: 90%;
    padding: 15px;
}
</style>