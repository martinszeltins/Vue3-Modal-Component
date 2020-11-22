<template>
    <button @click="myModal = true">Open modal</button>

    <modal v-model="myModal">
        <div class="my-content">
            Hello world!
            <button @click="myModal = !myModal">Close modal</button>
        </div>
    </modal>
</template>

<script>
    import { ref } from 'vue'
    import Modal from './components/Modal.vue'

    export default {
        components: {
            Modal
        },

        setup()
        {
            const myModal = ref(false)

            return { myModal }
        }
    }
</script>

<style>
    .my-content {
        background: #fff;
        padding: 12px 20px;
        border-radius: 8px;
    }
</style>