<template>
  <div v-if="addModalActive" class="modal">
    <div class="modal-bg">
      <div class="modal-header">
        <h3>Novo relatório</h3>
        <button class="exit-btn" @click="closeModal">
          <v-icon color="#312F2F">mdi-close-circle</v-icon>
        </button>
      </div>

      <div class="modal-body">
        <form action="#">
          <label for="subject" class="form-label">Assunto
            <input type="text" class="form-field" id="subject">
          </label>
          <label for="author" class="form-label">Autor
            <input type="text" class="form-field" id="author">
          </label>
          <label for="author" class="form-label">Departamento
            <select class="form-field">
              <option value="fn">Financeiro</option>
              <option value="rh">Recursos Humanos</option>
              <option value="ti">TI</option>
            </select>
          </label>
          <label for="date" class="form-label">Data
             <input type="date" class="form-field" id="date">
          </label>
          <label for="report" class="form-label">Relatório
             <input type="file" class="form-field" id="report">
          </label>

          <div class="modal-footer">
            <button type="submit" class="submit-btn">Salvar</button>
          </div>
        </form>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'AddNewModal',

  props: [ 'addModalActive', 'closeModal' ]
}
</script>

<style scoped>
  .modal {
    position: fixed;
    top: 0;
    left: 0;
    display: flex;
    justify-content: center;
    align-items: center;
    width: 100%;
    min-height: 100%;
    padding: 2rem;
    border-radius: 0.2rem;
    background: rgba(0, 0, 0, 0.7);
    color: #312F2F;
    z-index: 1;
  }
  .modal-bg {
    display: flex;
    flex-direction: column;
    align-items: center;
    width: 80%;
    height: 100%;
    padding: 2rem 1rem;
    border-radius: 0.2rem;
    background: #FFF;
    box-shadow: 
      0px 4px 6px -4px rgba(24, 39, 75, 0.12), 
      0px 8px 8px -4px rgba(24, 39, 75, 0.08);
  }
  .modal-header {
    display: flex;
    justify-content: space-between;
    align-items: center;
    width: 85%;
    padding-bottom: 1.2rem;
    font-size: 1.2rem;
    border-bottom: 1px solid #DDD;
  }
  .modal-body {
    width: 100%;
    height: 80%;
    display: flex;
    justify-content: center;
    align-items: center;
  }
  form {
    display: flex;
    flex-flow: row wrap;
    justify-content: space-between;
    width: 85%;
    min-height: 80%;
    padding: 1rem 2rem;
  }
  .form-label {
    flex: 1 1 100%;
    height: fit-content;
    font-size: 1rem;
  }
  .form-field {
    width: 100%;
    margin: 1rem 0;
    padding: 0.5rem 1rem;
    border-radius: 0.2rem;
    background: #EEE;
    color: #312F2F;
  }
  .form-label:nth-child(2), 
  .form-label:nth-child(3),
  .form-label:nth-child(4), 
  .form-label:nth-child(5){
    flex: 1 1 47%;
    margin: 0.5rem;
  }
  .modal-footer {
    display: flex;
    justify-content: center;
    width: 100%;
    margin-top: 1rem;
  }
  .submit-btn {
    padding: 0.5rem 2rem;
    border-radius: 0.2rem;
    background: #312F2F;
    color: #FFF;
  }
  .submit-btn:hover {
    background: #F1D77E;
    color: #312F2F;
  }
</style>