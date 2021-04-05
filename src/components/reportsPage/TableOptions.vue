<template>
  <div class="table-options align-center">
    <div class="table-organize align-center">
      <input type="text" placeholder="Buscar ..." class="reports-search" @keyup="search($event.target.value)"/>
      <label for="dropdown-menu" class="sort-label align-center" @click="dropdownActive = !dropdownActive">
        Ordenar por: 
          <span class="sort-choosed">{{ dataOrder[orderOption] }}</span> 
          <v-icon color="#FFF"> mdi-menu-down </v-icon>
        <div v-if="dropdownActive" id="dropdown-menu" >
          <p @click="changeOrder(0); sortData(orderOption)" class="dropdown-menu-item">Data</p>
          <p @click="changeOrder(1); sortData(orderOption)" class="dropdown-menu-item">Departamento</p>
        </div>
      </label>
    </div>
    <div class="table-actions align-center">
      <button class="table-actions-btn" title="Deletar">
        <v-icon color="#F1D77E">mdi-file-edit-outline</v-icon>
      </button>
      <button class="table-actions-btn" title="Editar">
        <v-icon color="#F1D77E">mdi-delete-outline</v-icon>
      </button>
      <button class="table-actions-btn" title="Adicionar">
        <v-icon color="#F1D77E">mdi-plus-box</v-icon>
      </button>
    </div>
  </div>
</template>

<script>
export default {
  name: 'TableOptions',

  props: [ 'orderOption', 'dataOrder', 'changeOrder', 'sort', 'sortData', 'search' ],
  
  data: () => ({
    dropdownActive: false
  })
}
</script>

<style scoped>
  .align-center {
    display: flex;
    align-items: center;
  }
  .table-options {
    width: 100%;
    height: fit-content;
    flex-flow: row wrap;
    justify-content: space-evenly;
    padding: 0 1rem 1rem 1rem;
    border-radius: 0.2rem 0.2rem 0 0;
    background: #312F2F;
    box-shadow: 
      0px 4px 6px -4px rgba(24, 39, 75, 0.12), 
      0px 8px 8px -4px rgba(24, 39, 75, 0.08);
    font-size: 0.9rem;
  }
  .table-organize {
    flex: 0 1 85%;
    flex-flow: row wrap;
    justify-content: flex-start;
  }
  .reports-search {
    flex: 0 1 20rem;
    margin-top: 0.7rem;
    padding: 0.5rem;
    outline: none;
    border-radius: 0.2rem;
    background: #525050;
    color: #FFF;
  }
  .sort-label {
    min-width: 11.5rem;
    position: relative;
    margin: 0.7rem 0.5rem 0 0.5rem;
    padding: 0.34rem 1rem;
    border-radius: 0.2rem;
    background: #525050;
    color: #FFF;
  }
  .sort-choosed {
    margin: 0 0.5rem;
    color: #F1D77E;
  }
  #dropdown-menu {
    position: absolute;
    left: 0;
    bottom: -94px;
    width: 100%;
    padding: 0.5rem 1rem;
    border-radius: 0.2rem;
    background: #525050;
    z-index: 1;
  }
  .dropdown-menu-item {
    margin: 0.5rem 0 1rem 0;
  }
  .table-actions {
    justify-content: center;
  }
  .table-actions-btn {
    margin-top: 0.7rem;
    padding: 0 0.3rem;
  }

  @media (max-width: 900px) {
    .table-organize {
      flex: 1 1 100%;
      justify-content: center;
    }
  }
</style>