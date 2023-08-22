<template>
  <main class="columns is-gapless is-multiline">
    <div class="column is-one-quarter">
      <BarraLateral/>
    </div>
    <div class="column is-three-quarter">
      <FormularioComponent/>
      <div class="tarefas">
        <Task />
        <Task />
        <Task />
      </div>
    </div>
  </main>
</template>

<script lang="ts">
import { defineComponent } from "vue";
import BarraLateral from "./components/BarraLateral.vue";
import FormularioComponent from "./components/FormularioComponent.vue";
import Task from "./components/TasksList.vue";

export default defineComponent({
  name: "App",
  components: {
    BarraLateral,
    FormularioComponent,
    Task,
  },
});
</script>

<style></style>
