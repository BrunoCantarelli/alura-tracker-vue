<template>
  <div class="is-flex is-aling-items-center is-justify-content-space-between">
    <CronometroComponent :tempoEmSegundos="tempoEmSegundos" />
    <button class="button" @click="iniciar" :disabled="cronometroRodando">
      <span class="icon">
        <i class="fas fa-play"></i>
      </span>
      <span>Play</span>
    </button>
    <button class="button" @click="finalizar" :disabled="!cronometroRodando">
      <span class="icon">
        <i class="fas fa-pause"></i>
      </span>
      <span>Stop</span>
    </button>
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";
import CronometroComponent from "./Cronometrocomponent.vue";

export default defineComponent({
  name: "ControlTime",
  components: { CronometroComponent },
  emits: ["aoFinalizarCronometro"],
  data() {
    return {
      tempoEmSegundos: 0,
      cronometro: 0,
      cronometroRodando: false,
    };
  },

  methods: {
    iniciar() {
      this.cronometro = setInterval(() => {
        this.cronometroRodando = true;
        this.tempoEmSegundos += 1;
      }, 1000);
    },
    finalizar() {
      this.cronometroRodando = false;
      clearInterval(this.cronometro);
      this.$emit("aoFinalizarCronometro", this.tempoEmSegundos);
      this.tempoEmSegundos = 0;
    },
  },
});
</script>
<style></style>
