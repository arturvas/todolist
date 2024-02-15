<script setup>
const props = defineProps([
  "cadastraTarefa",
  "tarefaTemp",
  "trocarFiltro",
  "editaTarefaTemp",
]);
</script>

<template>
  <form @submit.prevent="props.cadastraTarefa">
    <div class="row">
      <div class="col-md-8 mb-2">
        <input
          :value="props.tarefaTemp"
          @change="props.editaTarefaTemp"
          required
          type="text"
          class="form-control"
          placeholder="Digite aqui a descrição da tarefa"
        />
      </div>
      <div class="col-md-4 d-flex">
        <div class="col-md-auto me-3">
          <button class="btn btn-outline-primary">Add +</button>
        </div>
        <div class="col">
          <select @change="props.trocarFiltro" class="form-select">
            <option value="Todas">Todas</option>
            <option value="Pendentes">Pendentes</option>
            <option value="Finalizadas">Finalizadas</option>
          </select>
        </div>
      </div>
    </div>
  </form>
</template>
