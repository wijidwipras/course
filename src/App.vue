<template>
  <div id="app">
    <b-container>
      <!-- navbar -->
      <b-navbar class="navbar-main" toggleable="lg" type="dark">
          <b-navbar-brand href="#">
            <img class="logo-icon" :src="Logo" alt="Logo" />
          </b-navbar-brand>

          <b-navbar-toggle target="nav-collapse"></b-navbar-toggle>

          <b-collapse id="nav-collapse" is-nav>
            <b-navbar-nav class="mx-auto">
              <router-link class="nav-link" to="/">Home</router-link>
              <router-link class="nav-link" to="/course">Course</router-link>
              <!-- <router-link class="nav-link" to="/about">About</router-link> -->
            </b-navbar-nav>

            <b-navbar-nav class="ml-auto">
              <router-link class="nav-link btn-su" to="#">
                <b-button>Sign Up</b-button>
              </router-link>
            </b-navbar-nav>

          </b-collapse>
        </b-navbar>
        <router-view />

    </b-container>
  </div>
</template>

<script>
import Logo from "@/assets/LogoBaru.png";

export default {
  data() {
    return {
      Logo: Logo,
    };
  },
};
</script>

<style>
#app {
  font-family: 'Source Sans 3', sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;

  /* height: 140vh; */
  background: linear-gradient(180deg, #192653 0%, #131d41 100%);
  color: #fff;
}

.navbar-main {
  display: flex;
  justify-content: center;
}

nav a {
  font-weight: bold;
  color: #2c3e50;
}

nav a.router-link-exact-active {
  color: #42b983;
}

.nav-link {
  font-family: "Source Sans 3", sans-serif;
  font-size: 16px;
  font-style: normal;
  font-weight: 600;
  line-height: normal;
}

.logo-icon {
  width: 150px;
  height: auto;
}

.btn-su {
  padding: 10px 25px;
  border-radius: 8px;
  background: rgba(255, 255, 255, 0.1);
}
</style>
