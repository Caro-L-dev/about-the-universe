<script>
export default {
  name: 'AppNavbar',
  props: {},
  data() {
    return {

    }
  },
  methods: {

  },
  mounted() {

  }
}
</script>

<template>
  <!-- <router-view /> -->
  <div class="navbar-height"></div>
  <div class="navbar">
    <div class="contain-burger">
      <div class="burger"></div>
    </div>
    <nav class="nav">
      <img routerLink="" routerLinkActive="active" class="pointer" src="../assets/logotype.png" alt="Logotype SpaceX" />
      <router-link to="/">Accueil</router-link>
      <router-link to="/next-mission">Prochaine mission</router-link>
    </nav>
  </div>
  <nav class="vertical-navbar">
    <a routerLink="/index-show-planets" routerLinkActive="active" class="nav-vertical-link">
      <span class="fas fa-globe fa-3x"></span>
      <p>Planètes</p>
    </a>
    <a routerLink="/index-show-vehicles" routerLinkActive="active" class="nav-vertical-link">
      <span class="fas fa-rocket fa-3x"></span>
      <p>Véhicules</p>
    </a>
    <a routerLink="/index-show-peoples" routerLinkActive="active" href="#" class="nav-vertical-link">
      <span class="fab fa-reddit-alien fa-3x"></span>
      <p>Personnes</p>
    </a>
  </nav>
</template>
