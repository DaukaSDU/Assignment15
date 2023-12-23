<template>
    <button :style="{backgroundColor: color}" class="flex justify-center items-center gap-2 bg-orange-300 py-2.5 px-4 rounded-3xl text-white">        
        <slot>Button</slot>
    </button>
</template>

<script>
    export default {
        props: {
            color: String
        }
    }
</script>