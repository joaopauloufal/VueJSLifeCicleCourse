<template>
    <div>
        {{nome}}
        <h1 @click="clique">Campeonato Brasileiro - Série A</h1>
    </div>
</template>

<script>
export default {
    name: 'titulo',

        data(){
            return {
                nome: 'João Paulo',
                variavel: null
            }
        },

        beforeCreate(){
            // Criar coisas no this
            // Verificar se o usuario está autenticado para definir configurações
            // Verificar informacoes no localstorage
            window.console.log(Object.assign({}, this),'beforeCreate');
        },

        created(){
            //this.variavel = new Date();
            window.console.log(Object.assign({}, this),'created');
        },

        beforeMount(){
            window.console.log(Object.assign({}, this),'beforeMount');
        },

        mounted(){
            window.console.log(Object.assign({}, this),'mounted');
        },

        beforeUpdate(){
            window.console.log(Object.assign({}, this),'beforeUpdate');
        },

        updated(){
            window.console.log(Object.assign({}, this),'updated');
        },

        beforeDestroy(){
            window.console.log(Object.assign({}, this),'beforeDestroy');
        },

        destroyed(){
            window.console.log(Object.assign({}, this),'destroyed');
        },

    methods: {

        clique(){
            this.nome = 'João Paulo Ferreira';
            window.console.log(this.$parent.$parent.param1);
        }

    }
}
</script>