<template>
    <div @click.self="closeModal" class="modal_bg">
        <div class="modal">
            <h1>{{entete}}</h1>
            <p>{{text}}</p>
            <div class="actions">
                <slot name="liens"></slot>
            </div>
        </div>
    </div>
</template>

<script>
    export default{
        props: ['entete','text'],
        methods: {
            closeModal(){
                this.$emit('close')
            }
        }
    }
</script>

<style>
    .modal_bg{
        background: #afc;
        width: 100%;
        padding-top: 0.5px;
    }
    .modal{
        width: 400px;
        margin: 10px auto;
        background: #fff;
        border-radius: 10px;
    }
    .modal h1{
        font-size: 2rem;
        color: bisque;
    }
    p{
        font-size: 2rem;
        font-style: italic;
    }
</style>