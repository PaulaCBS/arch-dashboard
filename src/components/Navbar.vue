<template>
  <div class="menu">
    <a href="#" class="menu-card" v-for="option in menu" :key="option.name">
      <div class="menu-icon-container">
        <img :src="option.icon" :alt="option.name" class="menu-icon"/>
      </div>
      <p>{{ option.name }}</p>
    </a>

    <router-link to="/reports" class="menu-card">
      <div class="menu-icon-container">
        <img src="../assets/icons/reports.svg" alt="relatórios" class="menu-icon"/>
      </div>
      <p>Relatórios</p>
    </router-link>
  </div>
</template>

<script>
export default {
  name: 'Navbar',
  data: () => ({
    menu: [
      { name: 'Usuários', icon: require('../assets/icons/users.svg') },
      { name: 'Serviços', icon: require('../assets/icons/services.svg') },
      { name: 'Conteúdos', icon: require('../assets/icons/content.svg') },
      { name: 'Eventos', icon: require('../assets/icons/events.svg') }
    ]
  })
}
</script>

<style scoped>
.menu {
    display: flex;
    flex-flow: row wrap;
    justify-content: center;
    align-items: flex-end;
    width: 100%;
    height: fit-content;
    margin: 1.2rem 0 0.5rem 0;
    padding: 0 1rem;
    background: #FFFF;
    box-shadow: 
      0px 2px 4px -1px rgba(24, 39, 75, 0.12), 
      0px 4px 12px -2px rgba(24, 39, 75, 0.1);
  }
  .menu-card {
    width: 12rem;
    height: 4.2rem;
    display: flex;
    justify-content: space-evenly;
    align-items: center;
    padding: 0 2.4rem;
    text-decoration: none;
    color: #312F2F;
  }
  .menu-card:hover {
    border-bottom: 4px solid #F1D77E;
  }
  .menu-icon-container {
    padding: 0.5rem 0.3rem;
    border-radius: 0.2rem;
  }
  .menu-icon {
    width: 2rem;
  }
  @media (max-width: 975px) {
    .menu {
      display: flex;
      flex-flow: row-reverse wrap;
    }
  }
</style>