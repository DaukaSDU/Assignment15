<template>
    <div
        :style="{
            display: 'flex',
            flexDirection: direction,
            width: width,
            gap: gap
        }"
    >
        <v-button
            @click="sendContent(button.id)" 
            :id="button.id" 
            :color="button.color" 
            v-for="button in buttons"
        >
            <img :src="button.src" :alt="button.alt">
            {{ button.text }}
        </v-button>
    </div>
</template>

<script>
    import VButton from './Buttons/VButton.vue';

    export default {
        components: {
            VButton
        },
        props: {
            direction: String,
            buttons: {
                type: Array,
                default: [
                    {
                        src: null,
                        alt: null,
                        text: 'Button 1',
                        color: null,
                        id: null
                    },
                    {
                        src: null,
                        alt: null,
                        text: 'Button 2',
                        color: null,
                        id: null
                    },
                    {
                        src: null,
                        alt: null,
                        text: 'Button 3',
                        color: null,
                        id: null
                    }
                ]
            },
            width: String,
            gap: String
        },
        methods: {
            sendContent(id) {
                this.$emit('getContent', id)
            }
        },
        emits: ['getContent']
    }
</script>