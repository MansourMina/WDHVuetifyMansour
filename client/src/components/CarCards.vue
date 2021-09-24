<template>
  <div>
    <div class="d-flex flex-wrap justify-content-center">
      <CarCard :c="c" v-for="c of cars" :key="c.id" @buyCar="buyCar" />
    </div>
  </div>
</template>

<script>
import CarCard from '@/components/CarCard.vue';
import axios from 'axios';
export default {
  name: 'CarCards',
  props: {
    cars: {
      type: Array,
    },
    refresh: {
      type: Function,
    },
  },
  components: {
    CarCard,
  },

  methods: {
    async buyCar(c) {
      await axios({
        url: 'http://localhost:3000/cars/' + c.id,
        method: 'PATCH',
        contentType: 'application/json',
        data: {
          title: c.title + ' RESERVED',
        },
      });
      this.refresh();
    },
  },
};
</script>
<style></style>
