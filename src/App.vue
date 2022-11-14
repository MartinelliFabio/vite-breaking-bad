<template>
  
  <header>
    <HeaderComponent/>
  </header>
  <main>
    <SearchComponent/>
    <ContainerCardComponent/>
    <CardComponent/>
  </main>

</template>

<script>
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
      apiUrl: 'https://www.breakingbadapi.com/api/characters'
    }
  }
</script>

<style lang="scss" scoped>

</style>