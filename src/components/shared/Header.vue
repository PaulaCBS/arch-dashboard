<template>
  <header class="header golden-border">
      <h1>
        <router-link to="/" class="logo-link" title="ArcH">
          <img src="logo-light.png" alt="ArcH" class="logo-img" />
        </router-link>
      </h1>

      <div class="search-wrapper d-flex justify-center align-center">
        <v-text-field
          flat
          dark
          solo-inverted
          hide-details
          color="#D79D39"
          append-icon="mdi-magnify"
          label="Buscar ..."
        ></v-text-field>
      </div>

      <div class="d-flex flex-row justify-space-between align-center">

      <div class="user">
        <div class="user-account-options">
          <v-btn icon dark class="user-account-options-btn" title="notificações">
            <v-icon>
              mdi-bell-outline
            </v-icon>
          </v-btn>
          <v-btn icon dark class="user-account-options-btn" title="sair">
            <v-icon>
              mdi-exit-to-app
            </v-icon>
          </v-btn>
        </div>

        <div class="user-account-info">
          <v-avatar>
            <img src="../../assets/images/pisani.jpg" alt="Pisani" />
          </v-avatar>
          <div class="d-flex flex-column justify-center">
            <p class="user-greeting">Boas-vindas,</p>
            <p class="user-name">Carlos Eduardo Pisani</p>
          </div>
        </div>
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
    padding: 0 7%;
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
    display: flex;
    align-items: center;
    color: #FFF;
  }
  .logo-img {
    max-width: 4.8rem;
  }
  .search-wrapper {
    min-width: 25rem;
    margin: 0.5rem;
  }
  .user {
    display: flex;
    justify-content: center;
    align-items: center;
    margin: 0.5rem 0;
  }
  .user-account-options {
    display: flex;
    justify-content: center;
    align-items: center;
    margin-right: 1rem;
  }
  .user-account-options-btn {
    margin: 0 0.5rem;
  }
  .user-account-info {
    display: flex;
    align-items: center;
    min-width: 14rem;
  }
  .user-greeting {
    margin: 0 0.7rem;
    font-size: 0.7rem;
    color: #BCBCBC;
  }
  .user-name {
    margin: 0 0.7rem;
    font-size: 0.9rem;
  }

  @media (max-width: 500px) {
    .header {
      justify-content: center;
    }
    h1 {
      display: flex;
      justify-content: center;
      width: 100%;
      margin: 1.5rem 0;
    }
  }
  @media (max-width: 990px) {
    .search-wrapper {
      order: 3;
      display: flex;
      justify-content: center;
      width: 100%;
      margin: 1.5rem 0;
    }
  }
</style>
