<template>
  <nav>
    <h1><router-link class="home-link" to="/">Home</router-link></h1>
    <ul>
      <li><router-link class="nav-link" to="/about">About</router-link></li>
      <li>
        <router-link class="nav-link" to="/countries">Countries</router-link>
      </li>
    </ul>
  </nav>
</template>

<script>
export default {
  name: 'Navbar',
};
</script>

<style lang="scss" scoped>
nav {
  display: flex;
  justify-content: space-between;
  height: 80px;
  align-items: center;
  background-color: $primary-color;

  h1 {
    font-size: 3rem;
    position: relative;
    left: 25px;

    .home-link {
      color: $secondary-color;
      text-decoration: none;
    }

    .router-link-exact-active {
      color: $third-color;
    }
  }

  ul {
    list-style-type: none;
    display: flex;
    flex-direction: row;

    li {
      margin: 0 10px;

      .nav-link {
        color: $secondary-color;
        text-decoration: none;
        padding: 10px 15px;
        border-radius: 24px;
        transition: 0.3s ease all;

        &:hover {
          background-color: $fourth-color;
        }
      }

      .router-link-exact-active {
        color: $third-color;
      }
    }
  }
}

@media (max-width: 662px) {
  nav {
    ul {
      li {
        margin: 0;

        .nav-link {
          padding: 5px 10px;
        }
      }
    }
  }
}
</style>
