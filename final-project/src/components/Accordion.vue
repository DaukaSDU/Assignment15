<template>
    <div class="accordions">
        <div class="accordion" v-for="accordion in accordions">
            <div @click="toggleContent(accordion.id)" class="cursor-pointer hover:bg-green-700 flex justify-between items-center bg-green-500 text-white">
                <slot>
                    Content
                </slot>
                <DropdownButton :active="active" :id="accordion.id" class="bg-yellow-500/0" />
            </div>
            <div :id="accordion.id + '-content'" style="transition: all .1s linear;" class="h-0 overflow-y-auto flex flex-wrap break-all bg-green-100">
                <slot></slot>
                {{ accordion.content }}
            </div>
        </div>
    </div>
</template>

<script>
    import DropdownButton from './Buttons/DropdownButton.vue';

    export default {
        data() {
            return {
                active: false
            }
        },  
        components: {
            DropdownButton
        },
        props: {
            accordions: {
                type: Array,
                default: [
                    {
                        id: 'accordion',
                        content: 'SSSSUUUUUUIIIIIIIIIIIIIIIIIIIIISSSSUUUUUUIIIIIIIIIIIIIIIIIIIIISSSSUUUUUUIIIIIIIIIIIIIIIIIIIIISSSSUUUUUUIIIIIIIIIIIIIIIIIIIIISSSSUUUUUUIIIIIIIIIIIIIIIIIIIIISSSSUUUUUUIIIIIIIIIIIIIIIIIIIIISSSSUUUUUUIIIIIIIIIIIIIIIIIIIIISSSSUUUUUUIIIIIIIIIIIIIIIIIIIIISSSSUUUUUUIIIIIIIIIIIIIIIIIIIIISSSSUUUUUUIIIIIIIIIIIIIIIIIIIIISSSSUUUUUUIIIIIIIIIIIIIIIIIIIIISSSSUUUUUUIIIIIIIIIIIIIIIIIIIIISSSSUUUUUUIIIIIIIIIIIIIIIIIIIIISSSSUUUUUUIIIIIIIIIIIIIIIIIIIIISSSSUUUUUUIIIIIIIIIIIIIIIIIIIIISSSSUUUUUUIIIIIIIIIIIIIIIIIIIIISSSSUUUUUUIIIIIIIIIIIIIIIIIIIII'
                    }
                ]
            }
        },
        methods: {
            toggleContent(id) {
                const content = document.getElementById(id + '-content');
                if (this.active = !this.active) {
                    content.style.height = '120px';
                } else {
                    content.style.height = '0px';
                }
            }
        }
    }
</script>