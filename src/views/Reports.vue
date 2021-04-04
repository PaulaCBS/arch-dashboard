<template>
  <main class="main">
    <div class="reports-manager">
      <div class="page-info">
        <h2 class="page-title">Relatórios</h2>
        <router-link to="/" class="back-btn">Voltar</router-link>
      </div>
      
      <div class="table-container">
        <TableOptions :dataOrder="dataOrder" :dataOption="dataOption" :changeOrder="changeOrder" :sortData="sortData"/>
        <DataTable  :pagination="pagination"/>
      </div>

      <Pages :changePage="changePage" :page="page" :itemsPage="itemsPage" :totalPages="totalPages"/>
    </div>
  </main>
</template>

<script>
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
    page: 1,
    itemsPage: 9,
    dataOrder: ["Data", "Departamento"],
    dataOption: 0,
    reports: [
      { "id": 1,
        "subject": "Donec pulvinar posuere ligula ac feugiat", 
        "date": "02/08/2019",
        "department": "Financeiro",
        "author": "Jose Barbosa"
      },
      { "id": 2,
        "subject": "Curabitur vel enim massa", 
        "date": "15/12/2019",
        "department": "Recursos Humanos",
        "author": "Carlos Costa"
      },
      { "id": 3,
        "subject": "Aliquam iaculis dignissim consectetur", 
        "date": "22/03/2019",
        "department": "TI",
        "author": "Juliana Vieira"
      },
      { "id": 4,
        "subject": "Duis rhoncus laoreet posuere", 
        "date": "28/07/2020",
        "department": "Financeiro",
        "author": "Antônia Moreira"
      },
      { "id": 5,
        "subject": "Nam faucibus auctor nibh vitae pharetra", 
        "date": "02/11/2020",
        "department": "Recursos Humanos",
        "author": "Aline Reis"
      },
      { "id": 6,
        "subject": "Integer malesuada vitae quam in condimentum", 
        "date": "20/01/2021",
        "department": "TI",
        "author": "Paulo Teixeira"
      },
      { "id": 7,
        "subject": "Vivamus sed dignissim mauris", 
        "date": "15/10/2020",
        "department": "Financeiro",
        "author": "Marcos Machado"
      },
      { "id": 8,
        "subject": "Orci varius natoque penatibus et magnis", 
        "date": "06/06/2019",
        "department": "Recursos Humanos",
        "author": "Lucas Silva"
      },
      { "id": 9,
        "subject": "Proin aliquam ornare justo id feugiat", 
        "date": "30/04/2018",
        "department": "TI",
        "author": "Antônio Ramos"
      },
      { "id": 10,
        "subject": "Etiam scelerisque leo neque", 
        "date": "10/06/2020",
        "department": "Financeiro",
        "author": "Adriana Ferreira"
      },
      { "id": 11,
        "subject": "Sed sed arcu sed neque fermentum sollicitudin", 
        "date": "21/11/2020",
        "department": "Recursos Humanos",
        "author": "Luiz Nascimento"
      },
      { "id": 12,
        "subject": "Cras imperdiet volutpat odio vel posuere", 
        "date": "11/01/2019",
        "department": "TI",
        "author": "Juliana Fernandes"
      },
      { "id": 13,
        "subject": "Nam id massa massa", 
        "date": "14/09/2020",
        "department": "TI",
        "author": "Márcia Barros"
      },
      { "id": 14,
        "subject": "Nulla suscipit pretium tempus", 
        "date": "08/01/2021",
        "department": "Recursos Humanos",
        "author": "Ana Nunes"
      },
      { "id": 15,
        "subject": "Sed maximus tellus in interdum semper", 
        "date": "24/01/2021",
        "department": "Financeiro",
        "author": "José Alves"
      }
    ],
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
      return this.dataOption = option;
    },
    sortData: function(param) {
      if(param == 1) {
        return this.reports.sort( (prev, next) => {
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
        return this.reports.sort( (prev, next) => {
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
    }
  },
  computed: {
    pagination: function(){
      return this.sortData(this.dataOption).slice(
        (this.itemsPage*this.page) - this.itemsPage, 
        this.itemsPage*this.page
      )
    },
    totalPages: function(){
      return Math.ceil(this.reports.length/this.itemsPage)
    },
    
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