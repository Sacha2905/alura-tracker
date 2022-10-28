<template>
  <div class="box formulario">
    <div class="columns">
      <div
        class="column is-8"
        role="form"
        aria-label="Formulario para criacao de uma nova tarefa"
      >
        <input
          type="text"
          class="input"
          placeholder="Qual tarefa voce deseja inciar?"
          v-model="descricao"
        />
      </div>
      <div class="column">
        <!-- Emite o envento -->
        <Temporizador @aoTemporizadorFinalizado="finalizarTarefa"/>
      </div>
    </div>
  </div>
</template>

<script>
import { defineComponent } from 'vue'
import Temporizador from './Temporizador.vue'

export default defineComponent({
  /*eslint-disable-next-line*/
  name: 'Formulario',
  emits: ['aoSalvarTarefa'],
  components: {
    /*eslint-disable-next-line*/
   Temporizador
  },
  //Metodo que retorna o estado
  data () {
    return {
      descricao: ''
    }
  },
  methods: {
    finalizarTarefa (tempoDecorrido) {
      this.$emit('aoSalvarTarefa', {
        duracaoEmSegundos: tempoDecorrido,
        descricao: this.descricao
      })
      this.descricao = ''
    }
  },
});
</script>
<style>
.formulario {
   color: var(--texto-primario);
   background-color: var(--bg-primario)
}
</style>
