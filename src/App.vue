<template>
  
  <header>
    <HeaderComponent/>
  </header>
  <main>
    <SearchComponent/>
    <ContainerCardComponent/>
    <CardComponent :characters="characterList" :loading="loading"/>
  </main>

</template>

<script>
import axios from 'axios';
import HeaderComponent from './components/HeaderComponent.vue';
import SearchComponent from './components/SearchComponent.vue';
import ContainerCardComponent from './components/ContainerCardComponent.vue';
import CardComponent from './components/CardComponent.vue';

  export default {
    components: {
      HeaderComponent,
      ContainerCardComponent,
      SearchComponent,
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

</style>