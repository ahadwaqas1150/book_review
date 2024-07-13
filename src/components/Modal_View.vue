<template>
    <div class="backdrop" @click.self="closeModal">
        <div class="modal_view">
            <slot></slot>
            <div class="actions">
                <slot name="links"></slot>
            </div>
        </div>
    </div>
</template>
<script>
    export default{
    props: ["showModal","description"],
    setup(){
        // implemt the close modal function
        const closeModal = () => {
            this.$emit("close");
        }
        return {closeModal};
    }
}
        </script>
<style>
.modal_view{
    width: 400px;
    padding: 20px;
    margin: 100px auto;
    background: white;
    border-radius: 10px;
}
.backdrop{
    top: 0;
    position: fixed;
    background: rgba(0,0,0,0.5);
    width: 100%;
    height: 100%;
}
.modal_view h1{
    color: #03cfb4;
    border: none;
    padding: 0;
}
.modal_view p{
    font-style: normal;
}
.modal_view .actions{
    text-align: center;
    margin: 30px 0 10px 0;
}
.modal_view .actions a{
    color: #333;
    padding: 8px;
    border: 1px solid #eee;
    border-radius: 4px;
    text-decoration: none;
    margin: 10px;
}
.modal_view .actions a:hover{
    background: #0db19e;
}
</style>