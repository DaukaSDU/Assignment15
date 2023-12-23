<template>
    <form @submit.prevent="sendContent">
        <v-toggle 
            v-for="toggle in toggles" 
            :msg="toggle.msg"
            :id="toggle.id"
            :value="toggle.value"
            :checked="toggle.checked"
            @getContent="add"
        />
        <button>Submit</button>
    </form>
</template>

<script>
    import VToggle from './VToggle.vue';

    export default {
        data() {
            return {
                successes: null
            }
        },
        props: {
            toggles: {
                type: Array,
                default: [
                    {
                        msg: null,
                        id: null,
                        value: null,
                        checked: false
                    }
                ]
            }
        },
        components: {
            VToggle
        },
        methods: {
            add(content) {
                for (let toggle of this.toggles) {
                    if (toggle.id === content.id) {
                        toggle.checked = content.checked
                    }
                }
            },
            sendContent() {
                this.$emit('getContent', this.toggles)
            }
        },
        emits: ['getContent']
    }
</script>