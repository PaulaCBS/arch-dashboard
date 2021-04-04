<template>
  <div class="data-container">
    <table class="reports-table">
      <thead class="reports-table-header">
        <tr class="reports-table-row">
          <th class="reports-table-cell"><v-icon small>mdi-checkbox-marked-outline</v-icon></th>
          <th class="reports-table-cell">Assunto</th>
          <th class="reports-table-cell">Data</th>
          <th class="reports-table-cell">Departamento</th>
          <th class="reports-table-cell">Autor</th>
        </tr>
      </thead>
      <tbody class="reports-table-body">
        <tr v-for="report in pagination" :key="report.id" class="reports-table-row">
          <td class="reports-table-cell"><input type="checkbox"></td>
          <td class="reports-table-cell">{{ report.subject }}</td>
          <td class="reports-table-cell">{{ report.date }}</td>
          <td class="reports-table-cell">{{ report.department }}</td>
          <td class="reports-table-cell">{{ report.author }}</td>
        </tr>
      </tbody>
    </table>
  </div>
</template>

<script>
export default {
  name: 'DataTable',

  props: ['pagination', 'currentPage', 'itemsPage', 'pageOptions'],

}
</script>

<style scoped>
  .data-container {
    padding-bottom: 1rem;
    overflow: auto;
  }
  .reports-table {
    width: 100%;
    border-collapse: collapse;
    background: #f2f2f2;
    white-space: nowrap;
  }
  .reports-table-header {
    text-align: left;
    background: #F1D77E;
    color: #312F2F;
  }
  .reports-table-body {
    background: #FFF;
  }
  .reports-table-row {
    border-bottom: 1px solid #DDD;
  }
  .reports-table-cell {
    padding: 0.4rem 1rem;
  }
  tr.reports-table-row:nth-child(even) {
    background: #F2F2F2;
  }
  .table-options-btn {
    margin: 0 0.2rem;
  }
</style>