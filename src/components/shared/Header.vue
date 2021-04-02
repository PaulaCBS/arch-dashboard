<template>
  <header class="header golden-border">
      <v-toolbar-title>
        <router-link to="/" class="logo-link">
          <v-img src="../../assets/images/logo-light.png" alt="ArcH" max-width="4rem" />
        </router-link>
      </v-toolbar-title>

      <v-spacer></v-spacer>

      <div class="search-wrapper d-flex justify-center align-center">
        <v-text-field
          v-model="search"
          flat
          dark
          solo-inverted
          hide-details
          color="#D79D39"
          append-icon="mdi-magnify"
          label="Buscar ..."
        ></v-text-field>
      </div>

      <v-spacer></v-spacer>

      <div class="d-flex flex-row justify-space-between align-center">

        <div class="mx-5 d-flex justify-center align-center">
          <v-btn icon dark class="mx-2">
            <v-icon>
              mdi-bell-outline
            </v-icon>
          </v-btn>
          <v-btn icon dark class="mx-2">
            <v-icon>
              mdi-exit-to-app
            </v-icon>
          </v-btn>
        </div>

        <v-avatar>
          <img src="../../assets/images/pisani.jpg" alt="Pisani" />
        </v-avatar>
        <div class="d-flex flex-column justify-center">
          <p class="user-greeting mx-3 my-0">Boas-vindas,</p>
          <p class="user-name mx-3 my-0">Carlos Eduardo Pisani</p>
        </div>
      </div>

  </header>
</template>

<script>
export default {
  name: 'Header'
}
</script>

<style scoped>
  .header {
    display: flex;
    flex-flow: row wrap;
    justify-content: space-between;
    min-height: 3rem;
    padding: 0.7rem 6rem;
    align-items: center;
    background: #312F2F;
    color: #FFF;
  }
  a {
    text-decoration: none;
  }
  .golden-border {
    border-bottom: 4px solid #D79D39;
  }
  .logo-link {
    color: #FFF;
  }
  .search-wrapper {
    min-width: 25rem;
  }
  .user-greeting {
    font-size: 0.7rem;
    color: #BCBCBC;
  }
  .user-name {
    font-size: 0.9rem;
  }
</style>
