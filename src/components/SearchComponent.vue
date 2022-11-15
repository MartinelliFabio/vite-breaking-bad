<template>
    <div class="container mb-3">
        <form class="row row-cols-lg-auto g-3 align-items-center" @submit.prevent="searchCharacters">
            <div class="col-12">
                <label class="visually-hidden" for="characterName">Cerca Nome</label>
                <input type="text" class="form-control" placeholder="Cerca Nome">
            </div>
        
            <div class="col-12">
                <select class="form-select" v-model="search">
                    <option selected value="">Choose...</option>
                    <option :value="category" v-for="(category, index) in categoryOptions" :key="index">{{ category }}</option>
                </select>
            </div>
        
            <div class="col-12">
                <button type="submit" class="btn btn-primary">Submit</button>
            </div>
        
            <div class="col-12">
                <button type="reset" class="btn btn-primary" @click="resetSearch">Reset</button>
            </div> 
        </form>
    </div>
</template>

<script>
    export default {
        name: 'SearchComponent',
        data() {
            return {
                categoryOptions: [
                    'Breaking Bad',
                    'Better Call Saul'
                ],
                search: ''
            }
        },
        methods: {
            searchCharacters() {
                this.$emit('filterchar', this.search);
                console.log(this.search)
            },
            resetSearch() {
                this.search= '';
                this.$emit('filterchar', this.search);
            }
        }
    }
</script>

<style lang="scss" scoped>

</style>