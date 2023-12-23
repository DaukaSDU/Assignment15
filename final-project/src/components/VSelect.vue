<template>
    <select 
        v-model="selected"
        :name="name" 
        :id="id"
        :style="{
            padding: padding || '10px',
            width: width || '300px',
            height: height
        }"
        @change="sendContent"
    >
        <option v-for="option in options" :value="option.value">
            {{ option.content }}
        </option>
    </select>
</template>

<script>
    export default {
        data() {
            return {
                selected: null
            }
        },
        props: {
            name: String,
            id: String,
            padding: String, 
            width: String,
            height: String,
            options: {
                type: Array,
                default: [
                    {
                        content: '-No Selected-',
                        value: 'null'
                    },
                    {
                        content: 'Option 1',
                        value: 'a'
                    },
                    {
                        content: 'Option 2',
                        value: 'b'
                    },
                    {
                        content: 'Option 3',
                        value: 'c'
                    },
                    {
                        content: 'Option 4',
                        value: 'd'
                    }
                ]
            }
        },
        methods: {
            sendContent() {
                this.$emit('getContent', this.selected)
            }
        },
        watch: {
            selected() {
                console.log('Selected: ' + this.selected)
            }
        },
        emits: ['getContent']
    }
</script>