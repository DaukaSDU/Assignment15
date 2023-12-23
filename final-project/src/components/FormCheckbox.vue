<template>
    <form @submit.prevent="sendContent">
        <input 
            @change="(event) => this.checked = event.target.checked"
            type="checkbox" 
            :name="name" 
            :id="id"
        >
        <label :for="id">{{ label || 'Label' }}</label>
        <button>Submit</button>
    </form>
</template>

<script>
    export default {
        data() {
            return {
                checked: null
            }
        },
        props: {
            name: String,
            id: String,
            label: String
        },
        methods: {
            sendContent() {
                this.$emit('getContent', this.checked)
            }
        },
        emits: ['getContent']
    }
</script>