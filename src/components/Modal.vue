<template>
    <teleport to="body">
        <div
            v-if="modelValue"
            class="dobby-modal-overlay"
            :style="{ 'background-color': overlayColor }"
            @click.self="closeModal">

            <slot></slot>
        </div>
    </teleport>
</template>

<script>
    import { ref } from 'vue'

    export default {
        props:
        {
            modelValue: {
                type: Boolean,
                default: false,
            },

            overlayColor: {
                type: String,
                default: '#00000021',
            }
        },

        setup(props, { emit })
        {
            function closeModal()
            {
                emit('update:modelValue', false)
            }

            return { closeModal }
        },
    }
</script>

<style>
    .dobby-modal-overlay {
        position: fixed;
        width: 100%;
        height: 100%;
        left: 0;
        top: 0;
        display: flex;
        justify-content: center;
        align-items: center;
    }
</style>