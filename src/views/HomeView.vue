<script setup>
const nome = "Pedro Brito";
</script>

<template>
  <section>
    <h1>Agenda de Estudos</h1>
    <p><strong>{{ nome }}</strong></p>
    <p>
      Aplicação para organizar as tarefas de estudo do curso, anotando o que
      precisa ser feito em cada disciplina.
    </p>
    <RouterLink to="/tarefas">Ir para Minhas tarefas</RouterLink>
  </section>
</template>