<template>
    <div class="box">
        <div class="column">
            <div class="columns is-8" role="form" aria-label="Formulário para criação de uma nova tarefa">
                <input type="text" class="input custom-input" placeholder="Qual tarefa você deseja iniciar?" />
            </div>
        </div>
        <div class="column">
            <div class="is-flex is-align-items-center is-justify-content-space-between">
                <section>
                    <strong>
                        {{ tempoDecorrido }}
                    </strong>
                </section>
                <button class="button" @click="iniciar">
                    <span class="icon">
                        <i class="fas fa-play"></i>
                    </span>
                    <span>play</span>
                </button>
                <button class="button" @click="finalizar">
                    <span class="icon">
                        <i class="fas fa-stop"></i>
                    </span>
                    <span>stop</span>
                </button>
            </div>
        </div>
    </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue';

export default defineComponent({
    name: 'FormularioAcesso',
    data() {
        return {
            tempoEmSegundos: 0,
            cronometro: 0
        }
    },
    computed: {
        tempoDecorrido () : string{
            return new Date(this.tempoEmSegundos * 1000).toISOString().substr(11, 8)
        }
    },
    methods: {
        iniciar() {
            // Começar a contagem
            // 1 seg = 1000 ms
            this.cronometro = setInterval(() => {
                this.tempoEmSegundos += 1;
            }, 1000)
        },
        finalizar() {
            clearInterval(this.cronometro)
        }
    }
})

</script>

<style>
.box {
    background: #202123;
}

/* Estilos para o input */
.custom-input {
    color: #F0F0F0;
    /* Cor do texto branco */
}

.column:last-child .button {
    /* Estilos para os botões */
    background: #17181A;
    color: #F0F0F0;
    /* Cor do texto branco */
}

.column:last-child .icon {
    /* Estilos para os ícones */
    color: #F0F0F0;
    /* Cor do ícone branco */
}
</style>
