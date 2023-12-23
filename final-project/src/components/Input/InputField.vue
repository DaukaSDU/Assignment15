<template>
    <div class="input-container">
        <label class="input-label" :for="id">{{ label || 'Label' }}</label>
        <input class="input-field"
            v-model="content"
            :style="{
                width: width || '400px', 
                height: height || '30px',
                padding: padding || '20px 15px'
            }"
            :type="type || 'text'" 
            :id="id"
            :placeholder="placeholder || ''"
            @input="sendContent"
        />
        <slot></slot>
        <p class="input-validation">{{ validation || '' }}</p>

    </div>
</template>

<script>
    export default {
        data() {
            return {
                content: ''
            }
        },  
        props: {
            label: String,
            type: String,
            id: String,
            placeholder: String,
            validation: String,
            width: String,
            height: String,
            padding: String
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
    .input-container {
        font-family: 'Gill Sans', 'Gill Sans MT', Calibri, 'Trebuchet MS', sans-serif;
    }

    .input-label {
        font-size: 16px;
        margin: 5px;
        opacity: .7;
        display: block;
    }

    .input-field {
        font-size: 16px;
        border: 1.4px solid rgb(186, 186, 186);
        border-radius: 10px;
        transition: all .1s linear;
    }

    .input-validation {
        margin: 5px;
        font-weight: 100;
    }
</style>