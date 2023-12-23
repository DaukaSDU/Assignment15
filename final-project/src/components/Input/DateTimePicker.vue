<template>
    <input-field 
        @getContent="content => {
            date = new Date(content)
            this.$emit('getContent', date)
        }"
        :type="(time) ? 'datetime-local' : 'date'"
    />
</template>

<script>
    import InputField from './InputField.vue';

    export default {
        data() {
            return {
                date: null
            }
        },
        components: {
            InputField
        },
        props: {
            time: {
                type: Boolean,
                default: true
            }
        },
        emits: ['getContent']
    }
</script>

<style>

</style>