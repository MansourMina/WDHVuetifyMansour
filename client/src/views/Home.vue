<template>
<v-container>
  <LogoBar />
  <CarCards/>
  </v-container>
</template>

<script>
  import LogoBar from '../components/LogoBar.vue'
  import CarCards from '../components/CarCards.vue'

  export default {
    name: 'Home',

    components: {
      LogoBar,
      CarCards
    },
  }
</script>
