<template>
    <form class="form-ta" @submit.prevent="sendContent">
        <label :for="id">{{ label || 'Label' }}</label>
        <textarea 
            v-model="content"
            :name="name" 
            :id="id"
            :class="(resizable) ? '' : 'not-resizable'"
            :rows="rows"
            :cols="cols"
        >
        </textarea>
        <button>Submot</button>
    </form>
</template>

<script>
    export default {
        data() {
            return {
                content: ''
            }
        },
        props: {
            name: String,
            id: String,
            resizable: {
                type: Boolean,
                default: true
            },
            rows: Number,
            cols: Number,
            label: String
        },
        methods: {
            sendContent() {
                this.$emit('getContent', this.content)
            }
        },
        emits: ['getContent']
    }
</script>

<style>
    .form-ta > textarea.not-resizable {
        resize: none;
    }
</style>