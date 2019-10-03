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
                nome: 'João Paulo'
            }
        },

        beforeCreate(){
            window.console.log('beforeCreate');
        },

        created(){
            window.console.log('created');
        },

        beforeMount(){
            window.console.log('beforeMount');
        },

        mounted(){
            window.console.log('mounted');
        },

        beforeUpdate(){
            window.console.log('beforeUpdate');
        },

        updated(){
            window.console.log('updated');
        },

        beforeDestroy(){
            window.console.log('beforeDestroy');
        },

        destroyed(){
            window.console.log('destroyed');
        },

    methods: {

        clique(){
            this.nome = 'João Paulo Ferreira';
            window.console.log(this.$parent.$parent.param1);
        }

    }
}
</script>