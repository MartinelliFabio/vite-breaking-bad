<template>
    <section class="container card-container">
        <div class="container d-flex justify-content-center mt-4 mb-2">
            <div v-html="`Found ${characterList.length} characters`" class="found fw-bold"></div>
        </div>
        <CardComponent :characters="characterList" :loading="loading" />
    </section>
</template>

<script>
import axios from 'axios';
import CardComponent from './CardComponent.vue';

    export default {
        name: 'ContainerCardComponent',
        components: {
            CardComponent
        },
        data() {
            return {
                apiUrl: 'https://www.breakingbadapi.com/api/characters',
                characterList: [],
                loading: false
            }
        },
        methods: {
            getCharacters() {
                this.loading = true;
                axios.get(this.apiUrl).then(
                    (res) => {
                        this.characterList = [...res.data];
                        console.log(this.characterList)
                        this.loading = false
                    }
                ).catch((error) => {
                    console.log(error);
                })
            }
        },
        created() {
            this.getCharacters()
        }
    }
</script>

<style lang="scss" scoped>
@use '../assets/style/partials/variables' as*;

.card-container {
    background-color: $bg-white;
    padding: 20px 0;
}

.found {
    background-color: $bg-barra;
    color: $text-white;
    width: 90%;
    padding: 15px;
}
</style>