<template>
    <li class="list-group-item">
        <span>{{ filme.titulo }} | {{ filme.ano }}</span>
        <button @click="selecionar" class="btn btn-secondary float-right">Selecionar</button>
    </li>
</template>

<script>
import { eventBus } from './../main'
export default {
    // inheritAttrs: false,
    props: {
        filme: {
            type: Object,
            required: true
        }
        // Não acessa this.data
        // titulo: {
        //     type: String,
        //     required: true
        //     // default: 'Vingadores',
        //     // validator(filmeTitulo) {
        //     //     return filmeTitulo.includes('Marvel')
        //     // }
        //     // default() {
        //     //     return 'Vingadores'
        //     // }
        // },
        // ano: {
        //     type: Number,
        //     required: true
        // }
    },
    methods: {
        selecionar() {
            // this.$emit('selecionarFilme', this.filme)
            // eventBus.$emit('selecionarFilme', this.filme)
            eventBus.selecionarFilme(this.filme)
        }
    }
}
</script>