<template>
    <div class="box">
        <div class="columns">
            <div class="column">
                <div class="column is-8" role="form" aria-label="Formulário para criação de uma nova tarefa">
                    <input type="text" class="input" placeholder="Qual tarefa você deseja iniciar?">
                </div>
                <div class="column">
                    <div class="is-align-itens-center is-justyify-content-space-between">
                        <section>
                            <strong>00:00:00</strong>
                        </section>
                        <button class="button">
                            <span class="icon">
                                <i class="fas fa-play"></i>
                            </span>
                            <span>play</span>
                        </button>
                        <button class="button">
                            <span class="icon">
                                <i class="fas fa-stop"></i>
                            </span>
                            <span>stop</span>
                        </button>
                    </div>

                </div>
            </div>
        </div>
    </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";
export default defineComponent({
  name: "FormularioTarefas",
  data () {
    return {
      tempoEmSegundos: 0,
      cronometro: 0
    }
  },
  computed: {
    tempoDecorrido () : string {
      return new Date(this.tempoEmSegundos * 1000).toISOString().substr(11,8)
    }
  },
  methods: {
    iniciar () {
      // começar a contagem
      // 1 seg = 1000 ms
      this.cronometro = setInterval(() => {
        this.tempoEmSegundos += 1        
      }, 1000)
    },
    finalizar () {
      clearInterval(this.cronometro)
    }
  }
});
</script>