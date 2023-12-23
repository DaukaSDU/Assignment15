<template>
    <form @submit.prevent="sendContent">
        <label :for="id">{{ label || 'Label' }}</label>
        <v-select 
            @getContent="content => sendContent(content)"
            :id="id"
            :name="name"
            :padding="padding"
            :options="options"
            :width="width"
            :height="height"
        />
    </form>
</template>

<script>
    import VSelect from './VSelect.vue';

    export default {
        methods: {
            sendContent(content) {
                this.$emit('getContent', content)
            }
        },
        components: {
            VSelect
        },
        props: {
            name: String,
            id: String,
            padding: String, 
            width: String,
            height: String,
            options: Object,
            label: String
        },
        emits: ['getContent']
    }
</script>