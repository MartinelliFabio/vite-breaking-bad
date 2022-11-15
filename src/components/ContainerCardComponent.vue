<template>
    <SearchComponent @filterchar="getCharacters" />
    <section class="container card-container">
        <CounterComponent/>
        <CardComponent :characters="store.characterList" :loading="store.loading" />
    </section>
</template>

<script>
import axios from 'axios';
import CardComponent from './CardComponent.vue';
import SearchComponent from './SearchComponent.vue';
import CounterComponent from './CounterCompontent.vue'
import { store } from '../store';


    export default {
        name: 'ContainerCardComponent',
        components: {
            CardComponent,
            SearchComponent,
            CounterComponent
        },
        data() {
            return {
                store,
                endPoint: '/characters'
            }
        },
        methods: {
            getCharacters(category) {
                let options = null;
                if (category) {
                    options = {
                        params: {
                            category: category
                        }
                    } 
                }
                store.loading = true;
                const url = store.apiUrl + this.endPoint;
                axios.get(url, options).then(
                    (res) => {
                        store.characterList = [...res.data];
                        console.log(store.characterList)
                        store.loading = false
                    }
                ).catch((error) => {
                    store.loading = false;
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
</style>