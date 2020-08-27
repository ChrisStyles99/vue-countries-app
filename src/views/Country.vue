<template>
  <div class="single-country">
    <h1>{{country.name}}({{country.nativeName}})</h1>
    <img :src="country.flag">
    <p>Continent: {{country.region}}</p>
    <p>Area: {{country.area}} km^2</p>
    <router-link class="return-btn" to="/countries">Return to Country search</router-link>
  </div>
</template>

<script>
import axios from 'axios';

export default {
  data() {
    return {
      code: this.$route.params.code,
      result: '',
      country: ''
    }
  },
  async created() {
    this.result = await axios.get(`https://restcountries.eu/rest/v2/alpha/${this.code}`);
    this.country = this.result.data;
  },
}
</script>

<style lang="scss">
  .single-country {
    height: 100vh;
    text-align: center;

    .return-btn {
      text-decoration: none;
      padding: 10px 15px;
      background-color: $third-color;
      border-radius: 12px;
      color: $secondary-color;
      font-size: 1.2rem;
      transition: 0.3s ease all;

      &:hover {
        background-color: $fourth-color;
      }
    }
  }
</style>