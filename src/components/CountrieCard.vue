<template>
  <div class="template">
    <div class="card" v-for="(country, index) in countries" :key="index">
      <div class="card-header">
        <img :src="country.flag" alt="">
      </div>
      <div class="card-text">
        <h1>{{country.name}}</h1>
      </div>
      <div class="card-footer">
        <router-link :to="'/country/' + country.alpha2Code.toLowerCase()" class="country-link">See Country</router-link>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: ['countries']
}
</script>

<style lang="scss" scoped>
  .template {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    gap: 20px;
    margin: 20px;

    .card {
      display: grid;
      grid-template-rows: 1fr 60px 60px;
      box-shadow: 2px 4px 8px 2px rgba($color: #000000, $alpha: 0.5);
      border-radius: 12px;

      .card-header {
        img {
          width: 100%;
          height: 100%;
          object-fit: cover;
          border-radius: 12px 12px 0 0;
        }
      }

      .card-text {
        background-color: $primary-color;

        h1 {
          margin: auto;
        }
      }

      .card-footer {
        background-color: $primary-color;
        border-radius: 0 0 12px 12px;

        .country-link {
          padding: 10px;
          text-decoration: none;
          background-color: $third-color;
          color: $secondary-color;
          margin: auto;
          border-radius: 12px;
          transition: 0.3s ease all;

          &:hover {
            background-color: $fourth-color;
          }
        }
      }
    }
  }

  @media (max-width: 992px) {
    .template {
      grid-template-columns: 1fr 1fr;
    }
  }

  @media (max-width: 600px) {
    .template {
      grid-template-columns: 1fr;
    }
  }
</style>