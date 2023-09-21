<template>
    <div>
        <button @click="comentar">
            Comentar
        </button>
        <p>
            {{ comentario }}
        </p>
        <p>
            {{ detalhes }}
        </p>
    </div>
</template>

<script lang="ts">

import Vue from 'vue'
import Component from 'vue-class-component'
import { Prop } from 'vue-property-decorator'

@Component
export default class Comentarista extends Vue{
    public comentario = ''
    @Prop() public nome!: string

    public comentar(): void{
        this.comentario = 'Um mega comentário bem bacana!'
    }

    get detalhes(){
        return `Nome: ${this.nome}`
    }
}

</script>