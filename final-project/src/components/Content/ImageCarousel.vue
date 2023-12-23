<template>
    <div class="flex">
        <span class="flex justify-center items-center p-4 bg-gray-200" @click="() => {if (--curr < 0) curr = items.length - 1}">
            <img class="w-7" src="../../assets/images/left.svg">
        </span>

        <div class="flex">
            <span clas="overflow-hidden h-40 w-60" v-for="item in active_items">
                <img class="object-cover h-full w-full" :src="item.src" v-if="item.index === curr">
                <img class="opacity-40 object-cover h-full w-full" :src="item.src" v-else>
            </span>
        </div>

        <span class="flex justify-center items-center p-4 bg-gray-200" @click="() => {if (++curr >= items.length) curr = 0}">
            <img class="w-7" src="../../assets/images/right.svg">
        </span>
    </div>
</template>

<script>
    export default {
        data() {
            return {
                curr: 2
            }
        },
        props: {
            items: {
                type: Array,
                default: [
                    'https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcSYscfUBUbqwGd_DHVhG-ZjCOD7MUpxp4uhNe7toUg4ug&s',
                    'https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcRyzQyiesjovetiwqwjWzss8ZX_baOSHBOiAgZsevkiBw&s',
                    'https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcSsjv8k9FpJH5AvquxbVyd06B5UludsXYeHuTLTGllucw&s',
                    'https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcQq70AvDs-OIZrlcU0kAqvObihT8VhvedCurSyXCDCakQ&s',
                    'https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcRjk9v6uG9g5AEonjfD_kYL_yoU_H78-w93Vl_SY3USsjtHVT3PXGkEB_oIVAAzb9JiP5A&usqp=CAU',
                    'https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcQ6g3P5972LeN4_5J9Dua6oCYn3cBzjSUGys5dhj4qerMbHQY5-TRyMzrmuRe3m6SPz4WU&usqp=CAU',
                    'https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcSYG6wzy6xm2DHOAolh8oL43BIHUUtjz7pFg6PWhMslLGRlSZy6LlrNvtmpj8uk4Hd3c64&usqp=CAU'
                ]
            }
        },
        methods: {
            left(index) {
                if (--index < 0) index = this.items.length - 1
                return index
            },
            right(index) {
                if (++index >= this.items.length) index = 0
                return index
            }
        },
        computed: {
            active_items() {
                let ans = [];
                let indexes = [
                    this.left(this.left(this.curr)),
                    this.left(this.curr),
                    this.curr,
                    this.right(this.curr),
                    this.right(this.right(this.curr))
                ]
                for (let index of indexes) {
                    ans.push({
                        src: this.items[index],
                        index: index
                    })
                }
                return ans;
            }
        }
    }
</script>