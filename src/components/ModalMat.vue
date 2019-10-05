<template>
    <div class="modal">
        <div class="modal-content">
            <slot name="header"></slot>
            <slot></slot>
            <div class="modal-footer">
                <slot name="footer"></slot>
            </div>
        </div>
    </div>   
</template>

<script>
export default {

    name: 'modal-mat',

    mounted(){
        window.$(this.$el).modal();
    },


    data(){

        return {
            golsCasa : 0,
            golsFora: 0
        }

    },

    methods: {

        show(){
            this.getModal().open();
        },

        close(){
            this.getModal().close();
        },

        getModal(){
            return window.M.Modal.getInstance(this.$el);
        }
    }
    
}
</script>