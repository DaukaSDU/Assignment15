<template>
    <form @submit.prevent="sendContent">
        <fieldset>
            <legend>{{ msg || 'Something' }}</legend>

            <label :for="radio.id" v-for="radio in radios">
                <input v-model="selected" :id="radio.id" type="radio" :name="name" :value="radio.value">
                {{ radio.label || 'suii' }}
            </label>
        </fieldset>

        <button>Submit</button>
    </form>
</template>

<script>
    export default {
        data() {
            return {
                selected: null
            }
        },
        props: {
            msg: String,
            name: String,
            radios: {
                type: Array,
                default: [
                    {
                        label: 'Label 1',
                        value: 'a',
                        id: '1'
                    },
                    {
                        label: 'Label 2',
                        value: 'b',
                        id: '2'
                    },
                    {
                        label: 'Label',
                        value: 'c',
                        id: '3'
                    }
                ]
            }
        },
        methods: {
            sendContent() {
                for (let radio of this.radios) {
                    if (radio.value === this.selected) {
                        this.$emit('getContent', radio)
                        console.log('Submitted radiobutton ' + JSON.stringify(radio))
                        return
                    }
                }
                console.log('No one selected')
                this.$emit('getContent', null)
            }
        },
        emits: ['getContent']
    }
</script>