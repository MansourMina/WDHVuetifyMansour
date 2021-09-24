<template>
  <div>
    <div class="d-flex flex-wrap justify-content-center">
      <CarCard :c="c" v-for="c of cars" :key="c.id" />
    </div>
  </div>
</template>

<script>
import CarCard from '@/components/CarCard.vue';
export default {
  name: 'CarCards',
  props: {
    cars: {
      type: Array,
    },
  },
  components: {
    CarCard,
  },

  data: () => ({
    cars: [],
  }),
};
</script>
<style></style>
