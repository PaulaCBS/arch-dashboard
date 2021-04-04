<template>
  <div class="pages">
    <button class="pagination-btn" @click="changePage('subtract')">
      <v-icon>mdi-chevron-left</v-icon>
    </button>
    <button class="pagination-btn" 
            v-for="index in totalPages" 
            :key="index" 
            @click="changePage(Number(index))"> {{ index }}
    </button>
    <button class="pagination-btn" @click="changePage('add')">
      <v-icon>mdi-chevron-right</v-icon>
    </button>
  </div>
</template>

<script>
export default {
  name: 'Pages',

  props: [ 'changePage', 'page', 'itemsPage', 'totalPages' ]
}
</script>

<style scoped>
  .pages {
    align-self: flex-end;
    display: flex;
    justify-content: center;
    align-items: center;
    width: 100%;
    height: 3.5rem;
    margin: 1rem 0;
  }
  .pagination-btn {
    margin: 0 0.1rem;
    padding: 0.35rem 0.8rem;
    border-radius: 0.1rem;
    box-shadow: 
      0px 2px 4px -1px rgba(24, 39, 75, 0.12), 
      0px 4px 12px -2px rgba(24, 39, 75, 0.1);
    background: #FAFAFA;
  }
  .pagination-btn:first-child, .pagination-btn:last-child {
    padding: 0.2rem 0.3rem;
  }
  .pagination-btn:hover {
    border: 2px solid #F1D77E;
  }
</style>