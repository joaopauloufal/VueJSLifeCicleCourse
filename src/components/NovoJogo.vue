<template>
    <div>
        <button type="button" class="btn btn-primary" @click="criarNovoJogo" :disabled="loading">Novo Jogo</button>
        <button @click="$refs.modal.$destroy()">Destruir modal</button>
        <placar-modal-mat :time-casa="timeCasa" :time-fora="timeFora" ref="modal"></placar-modal-mat>
    </div>
</template>

<script>

import PlacarModalMat from './PlacarModalMat.vue';
import getTimes from '../get-times';


export default {

    name: 'novo-jogo',

    created(){
        getTimes.then(times => {
                this.times = times;
            })
            .finally(() => this.loading = false);

            window.console.log(this.times);
    },

    components: {
        PlacarModalMat
    },
    

    data(){
        return {
            loading: true,
            timeCasa: null,
            timeFora: null,
            //times: this.timesColecao
            times: []
        }
    },
    //props: ['times'],
    inject: ['timesColecao'],

    methods: {

        criarNovoJogo(){
            window.console.log(this.$refs);
            var indiceCasa = Math.floor(Math.random() * 20);
            var indiceFora = Math.floor(Math.random() * 20);

            // var timeCasa = this.$root.times[indiceCasa];
            // var timeFora = this.$root.times[indiceFora];
            //var timeCasa = this.timesColecao[indiceCasa];
            //var timeFora = this.timesColecao[indiceFora];

            this.timeCasa = this.times[indiceCasa];
            this.timeFora = this.times[indiceFora];

            var modal = this.$refs.modal;
            window.console.log(modal);
            modal.showModal();

            //this.$emit('novo-jogo', {timeCasa, timeFora});

        },

    }
    
}
</script>