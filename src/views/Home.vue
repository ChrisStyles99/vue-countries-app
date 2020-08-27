<template>
  <div class="home">
    <div class="text-class">
      <h1>Welcome to the countries directory</h1>
      <router-link to="/countries" class="countries-btn">View all countries</router-link>
    </div>
    <img src="https://images.pexels.com/photos/220201/pexels-photo-220201.jpeg" alt="">
  </div>
</template>

<script>

export default {
  name: 'Home',
  components: {
    
  }
}
</script>

<style lang="scss" scoped>
  .home {
    height: 100vh;
    position: relative;

    &::after {
      content: "";
      background: rgba($color: #000000, $alpha: 0.3);
      width: 100%;
      height: 100%;
      position: absolute;
      top: 0;
      left: 0;
    }

    .text-class {
      position: absolute;
      top: 50%;
      left: 50%;
      transform: translate(-50%, -50%);
      z-index: 3;

      h1 {
        font-size: 4rem;
        color: $secondary-color;
        -webkit-text-stroke: 1px $primary-color;
      }

      .countries-btn {
        padding: 10px 15px;
        background-color: $third-color;
        border: none;
        border-radius: 24px;
        font-size: 1.5rem;
        color: $secondary-color;
        text-decoration: none;
        transition: 0.3s ease all;
        cursor: pointer;

        &:hover {
          background-color: $fourth-color;
        }
      }
    }

    img {
      width: 100%;
      height: 100%;
      object-fit: cover;
      position: relative;
    }
  }
</style>
