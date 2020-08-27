<template>
  <div class="countries">
    <countrie-card :countries="countries"></countrie-card>
  </div>
</template>

<script>
import axios from 'axios';
import CountrieCard from '../components/CountrieCard.vue';

export default {
  data() {
    return {
      result: '',
      countries: ''
    }
  },
  components: {
    CountrieCard
  },
  async created() {
    this.result = await axios.get('https://restcountries.eu/rest/v2/all');
    this.countries = this.result.data;
  },
}
</script>

<style lang="scss" scoped>

</style>