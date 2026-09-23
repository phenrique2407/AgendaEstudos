<script setup>
import { ref } from "vue";

const novaTarefa = ref("");
const tarefas = ref([]);
let proximoId = 1;

function adicionar() {
  const texto = novaTarefa.value.trim();
  if (texto === "") return;

  tarefas.value.push({ id: proximoId++, texto });
  novaTarefa.value = "";
}
</script>

<template>
  <section>
    <h1>Minhas tarefas</h1>

    <div class="form">
      <input
        v-model.trim="novaTarefa"
        type="text"
        placeholder="Digite uma tarefa"
        @keyup.enter="adicionar"
      />
      <button @click="adicionar">Adicionar</button>
    </div>

    <ul>
      <li v-for="tarefa in tarefas" :key="tarefa.id">
        {{ tarefa.texto }}
      </li>
    </ul>

    <p v-if="tarefas.length === 0">Nenhuma tarefa ainda.</p>

    <RouterLink to="/">Voltar para o início</RouterLink>
  </section>
</template>

<style scoped>
.form {
  display: flex;
  gap: 8px;
  margin: 16px 0;
}

input {
  flex: 1;
  padding: 8px 10px;
  border: 1px solid #cbd2d9;
  border-radius: 6px;
  font-size: 1rem;
}

button {
  padding: 8px 16px;
  border: none;
  border-radius: 6px;
  background: #2b6cb0;
  color: #fff;
  font-size: 1rem;
  cursor: pointer;
}

ul {
  padding-left: 20px;
}

li {
  margin-bottom: 6px;
}
</style>