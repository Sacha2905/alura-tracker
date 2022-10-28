<template>
    <div class="box has-text-weight-bold" :style="estilos">
        <slot> </slot>
    </div>
</template>

<script>
import { defineComponent } from 'vue'

export default defineComponent({
   /*eslint-disable-next-line*/ 
   name: 'Box',
   data () {
    return {
        estilos: {
           backgroundColor: '#FAF0CA'
        }
    }
   }
})
</script>
