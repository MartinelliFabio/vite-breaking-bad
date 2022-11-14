<template>
  
  <header>
    <HeaderComponent/>
  </header>
  <main>
    <SearchComponent/>
    <ContainerCardComponent/>
    <!-- <CardComponent :characters="characterList" :loading="loading"/> -->
  </main>

</template>

<script>

import HeaderComponent from './components/HeaderComponent.vue';
import SearchComponent from './components/SearchComponent.vue';
import ContainerCardComponent from './components/ContainerCardComponent.vue';
// import CardComponent from './components/CardComponent.vue';

  export default {
    components: {
      HeaderComponent,
      ContainerCardComponent,
      SearchComponent,
      // CardComponent
    },
    
}
</script>

<style lang="scss" scoped>

</style>