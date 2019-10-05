<template>
  <div id="app">
    <div class="container">
        <button @click="mostrarTitulo = false">Destruir titulo</button>
        <titulo v-if="mostrarTitulo" id="teste" teste="João"></titulo>
        <div class="row">
            <div class="col-md-12">
                <novo-jogo :times="times"></novo-jogo>
            </div>
        </div>
        <br>
        <div class="row">
            <div class="col-md-12" v-show="visao === 'tabela'">
                <tabela-clubes :times="times"></tabela-clubes>
            </div>
        </div>
    </div>
  </div>
</template>

<script>

import Titulo from './components/Titulo.vue'
import NovoJogo from './components/NovoJogo.vue'
import TabelaClubes from './components/TabelaClubes.vue'

export default {
  name: 'app',
  components: {
    Titulo, NovoJogo, TabelaClubes
  },

  props: ['teste'],

  data(){

      return {
          mostrarTitulo: true,
          times: [],
          timeCasa: null,
          timeFora: null,
          visao : 'tabela',

      };

  },

  methods: {

      showTabela(event){
          window.console.log(event);
          this.visao = 'tabela';
      },

      showPlacar({timeCasa, timeFora}){
          this.timeCasa = timeCasa;
          this.timeFora = timeFora;
          this.visao = 'placar';
      },

      ordenar(indice){
          this.$set(this.ordem.orientacao, indice, this.ordem.orientacao[indice] == 'desc' ? 'asc':'desc');
      }

  },

  filters : {
      saldo(time){
          return time.gm - time.gs;
      }
  }

}
</script>
