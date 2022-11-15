<template>
  
  <header>
    <HeaderComponent/>
  </header>
  <main>
    <ContainerCardComponent/>
  </main>

</template>

<script>

import HeaderComponent from './components/HeaderComponent.vue';
import ContainerCardComponent from './components/ContainerCardComponent.vue';

  export default {
    components: {
      HeaderComponent,
      ContainerCardComponent,
    },
    
}
</script>

<style lang="scss" scoped>

</style>