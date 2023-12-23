<template>
    <button :class="(active ? 'active' : '')" :id="id" @click="() => active = !active" class="text-white transition p-5 flex justify-center items-center bg-orange-300 w-8 h-8 text-white rounded-3xl">
        <slot>
            <span>
                <svg class="fill-white" xmlns="http://www.w3.org/2000/svg" height="16" width="10" viewBox="0 0 320 512">
                    <path d="M310.6 233.4c12.5 12.5 12.5 32.8 0 45.3l-192 192c-12.5 12.5-32.8 12.5-45.3 
                    0s-12.5-32.8 0-45.3L242.7 256 73.4 86.6c-12.5-12.5-12.5-32.8 0-45.3s32.8-12.5 
                    45.3 0l192 192z"/>
                </svg>
            </span>
        </slot>
    </button>
</template>

<script>
    export default {
        data() {
            return {
                
            }
        },
        props: {
            active: {
                type: Boolean,
                default: false
            },
            id: {
                type: String,
                default: 'dropdown'
            }
        },
        methods: {
        }
    }
</script>

<style> 
[id].active {
    transform: rotate(90deg);
}
</style>