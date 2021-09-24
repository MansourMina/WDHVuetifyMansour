<template>
  <v-container>
    <LogoBar />
    <CarCards :cars="cars" :refresh="getCars" />
  </v-container>
</template>

<script>
import LogoBar from '../components/LogoBar.vue';
import CarCards from '../components/CarCards.vue';
import axios from 'axios';

export default {
  name: 'Home',

  components: {
    LogoBar,
    CarCards,
  },

  data: () => ({
    cars: [],
  }),

  created() {
    this.getCars();
  },
  methods: {
    async getCars() {
      const { data } = await axios({
        url: 'http://localhost:3000/cars',
        method: 'GET',
      });
      this.cars = data;
    },
  },
};
</script>
