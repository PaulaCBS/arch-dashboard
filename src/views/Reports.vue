<template>
  <main class="main">
    <div class="reports-manager">
      <div class="page-info">
        <h2 class="page-title">Relatórios</h2>
        <router-link to="/" class="back-btn">Voltar</router-link>
      </div>
      
      <div class="table-container">
        <TableOptions />
        <DataTable  :pagination="pagination"/>
      </div>

      <div class="pages">
        <button class="pagination-btn">
          <v-icon>mdi-chevron-left</v-icon>
        </button>
        <button class="pagination-btn" v-for="index in totalPages" :key="index">{{ index }}</button>
        <button class="pagination-btn">
          <v-icon>mdi-chevron-right</v-icon>
        </button>
      </div>
    </div>
  </main>
</template>

<script>
import TableOptions from '../components/reportsPage/TableOptions'
import DataTable from '../components/reportsPage/DataTable'

export default {
  name: 'Reports',

  components: {
    TableOptions,
    DataTable
  },

  data: () => ({
    page: 1,
    itemsPage: 9,
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
  computed: {
    pagination: function(){
      return this.reports.slice(
        this.itemsPage - (this.itemsPage - (this.page-1)), 
        this.itemsPage*this.page
      )
    },
    totalPages: function(){
      return Math.round(this.reports.length/this.itemsPage)
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
  .pages {
    align-self: flex-end;
    display: flex;
    justify-content: center;
    align-items: center;
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