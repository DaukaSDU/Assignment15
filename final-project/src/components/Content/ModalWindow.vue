<template>
    <div :style="{display: (active ? 'flex' : 'none')}" class="z-50 fixed top-0 flex justify-center items-center h-screen bg-black/50">
        <div class="rounded-xl bg-white w-2/3">
            <h3 class="text-2xl font-bold p-4 flex items-center justify-between">
                {{ title || 'Static Modal' }}
                <span class="text-base">
                    <v-button @click="active = false" color="gray">X</v-button>
                </span>
            </h3>
            <p class="p-4">
                {{ content || 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Quo saepe itaque voluptates facere, porro unde, enim vitae aperiam aliquid mollitia accusantium architecto. Quisquam obcaecati aliquam saepe dolor necessitatibus! Temporibus, voluptatibus autem facilis, quos sequi doloribus aperiam molestias explicabo unde qui enim ab quasi cum atque pariatur ipsam debitis quisquam aut mollitia quam. Non distinctio id, sint veritatis libero in ad praesentium dignissimos neque debitis optio possimus obcaecati nam veniam earum ab commodi, laboriosam voluptas illo ea? Porro, illo consequatur autem tenetur eaque totam necessitatibus aperiam praesentium, iure ullam, repudiandae quas consequuntur dolor nihil corporis. Dolor libero nesciunt rerum earum ex.' }}
            </p>
            <div class="flex p-4 gap-2">
                <v-button @click="active = false" color="blue">{{ b1 || 'Button 1' }}</v-button>
                <v-button @click="active = false" color="gray">{{ b2 || 'Button 2' }}</v-button>
            </div>
        </div>
    </div>
</template>

<script>
    import VButton from '/Users/dauletomar/Desktop/Frontend Projects/FinalProject/final-project/src/components/Buttons/VButton.vue'

    export default {
        components: {
            VButton
        },
        props: {
            title: String,
            content: String,
            b1: String,
            b2: String,
            active: Boolean
        }
    }
</script>