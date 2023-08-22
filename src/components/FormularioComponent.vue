<template>
  <div class="box">
    <div class="columns">
      <div class="column is-8" role="form" aria-label="Formulario">
        <input
          type="text"
          class="input"
          placeholder="Qual tarefa você deseja iniciar?"
          v-model="descricaoTarefa"
        />
      </div>
      <div class="column">
        <ControlTime @aoFinalizarCronometro="finalizarTarefa" />
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";
import ControlTime from "./ControlTime.vue";

export default defineComponent({
  name: "FormularioComponent",
  components: { ControlTime },
  data() {
    return {
      descricaoTarefa: "",
    };
  },
  methods: {
    finalizarTarefa(tempoDecorrido: number): void {
      console.log(tempoDecorrido);
      console.log(this.descricaoTarefa);
      this.descricaoTarefa = "";
    },
  },
});
</script>

<style></style>
