<template>
    <div class="container">
        <div v-if="loading">
            Sto caricando i dati
        </div>
        <div class="row" v-if="!loading">
            <div class="col-3" v-for="(item, index) in characters" :key="item.char_id">
                <div class="character">
                    <img :src="item.img" :alt="item.name">
                    <h3>{{ item.name }}</h3>
                    <h5>{{ item.category }}</h5>
                    <p>{{ item.status }}</p>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        name: 'CardComponent',
        props: ['characters', 'loading']
    }
</script>

<style lang="scss" scoped>

</style>