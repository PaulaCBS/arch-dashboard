<template>
  <main class="main">
    <div class="reports-manager">
      <div class="page-info">
        <h2 class="page-title">Relatórios</h2>
        <router-link to="/" class="back-btn">Voltar</router-link>
      </div>
      
      <div class="table-container">
        <TableOptions :dataOrder="dataOrder" 
                    :orderOption="orderOption" 
                    :changeOrder="changeOrder" 
                    :sortData="sortData"
                    :search="search"/>
        <DataTable  :pagination="pagination"/>
      </div>

      <Pages :changePage="changePage" 
             :page="page" 
             :itemsPage="itemsPage" 
             :totalPages="totalPages"/>
    </div>
  </main>
</template>

<script>
import data from "../assets/db.json";
import TableOptions from '../components/reportsPage/TableOptions'
import DataTable from '../components/reportsPage/DataTable'
import Pages from '../components/reportsPage/Pages'

export default {
  name: 'Reports',

  components: {
    TableOptions,
    DataTable,
    Pages
  },

  data: () => ({
    reports: data.reports,
    page: 1,
    itemsPage: 9,
    dataOrder: ["Data", "Departamento"],
    orderOption: 0,
    searchActive: false,
    searchTerm: ""
  }),
  methods: {
    changePage: function(param) {
      if(param == "add" && this.page != this.totalPages) {
        return this.page++
      } 
      if(param == "subtract" && this.page > 1) {
        return this.page--
      }
      if(typeof param == "number") {
        return this.page = param
      }
    },
    changeOrder: function(option){
      return this.orderOption = option;
    },
    sortData: function(param) {
      const data = this.searchActive ? (this.search(this.searchTerm)) : (this.reports)

      if(param == 1) {
        return data.sort( (prev, next) => {
          if(prev.department < next.department){
            return -1
          }
          if(prev.department > next.department){
            return 1
          }
          return 0
        })
      }
      if(param == 0 ) {
        return data.sort( (prev, next) => {
          prev = prev.date.split('/').reverse().join('');
          next = next.date.split('/').reverse().join('');
          if(prev < next){
            return 1
          }
          if(prev > next){
            return -1
          }
          return 0
        })
      }

    },
    search: function(param) {
      this.searchActive = true

      this.searchTerm = param

      const searchMatch = this.reports.filter( data => {
        return data.subject.match(this.searchTerm)
      })
      return searchMatch
    }
  },
  computed: {
    pagination: function(){
      return this.sortData(this.orderOption).slice(
        (this.itemsPage*this.page) - this.itemsPage, 
        this.itemsPage*this.page
      )
    },
    totalPages: function(){
      const totalItems = this.searchActive ? (this.search(this.searchTerm)) : (this.reports)
      return Math.ceil(totalItems.length/this.itemsPage)
    }
  }
}
</script>

<style scoped>
  .main {
    padding: 0 7%;
    color: #312F2F;
  }
  .reports-manager {
    width: 100%;
    display: flex;
    flex-flow: row wrap;
    justify-content: center;
    min-height: 38rem;
    margin: 2rem 0;
    padding: 2rem;
    background: #FFF;
    box-shadow: 
      0px 6px 14px -6px rgba(24, 39, 75, 0.12), 
      0px 10px 32px -4px rgba(24, 39, 75, 0.1);
  }
  .page-info {
    width: 100%;
    height: fit-content;
    display: flex;
    justify-content: space-between;
    align-items: center;
    margin-bottom: 2rem;
  }
  .page-title {
    font-size: 1.8rem;
  }
  .back-btn {
    color: #D79D39;
  }
  .back-btn:hover {
    color: #F1D77E;
  }
  .table-container {
    width: 100%;
    height: 80%;
  }
</style>