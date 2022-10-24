<template>
    <section>
        <strong>
            {{ tempoDecorrido }}
        </strong>
    </section>    
</template>

<script>
import { defineComponent } from 'vue'

export default defineComponent ({
    /*eslint-disable-next-line*/
    name: 'Cronometro',
    //propriedades
    props: {
        tempoEmSegundos: {
            type: Number,
            default: 0
        }
    },
    //componentes
    computed: {
        tempoDecorrido() {
            return new Date(this.tempoEmSegundos * 1000) .toISOString() .substr(11,8)
    }
  },
})
</script>