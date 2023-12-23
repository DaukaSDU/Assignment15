<template>
    <label :style="{fontFamily: ff}" class="p-1 ">
        Label
        <slot></slot>
    </label>
</template>

<script>
    export default {
        props: {
            ff: String
        }
    }
</script>