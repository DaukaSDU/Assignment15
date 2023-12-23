<template>
    <div 
        :style="{
            width: width, 
            fontSize: fz,
            display: (active) ? 'flex' : 'none'
        }" 
        class="z-50 absolute rounded-xl bg-gray-800 text-white flex w-fit p-2"
    >
        <span class="relative bottom-5 left-4">
            <svg xmlns="http://www.w3.org/2000/svg" fill="rgb(31 41 55)" height="24" width="15" viewBox="0 0 320 512">
                <path d="M182.6 137.4c-12.5-12.5-32.8-12.5-45.3 0l-128 128c-9.2 9.2-11.9 22.9-6.9 34.9s16.6 19.8 29.6 19.8H288c12.9 0 24.6-7.8 29.6-19.8s2.2-25.7-6.9-34.9l-128-128z"/>
            </svg>
        </span>
        {{ content || 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Animi eos vero dolorem iusto delectus, consequuntur quaerat recusandae qui ullam repellendus?' }}
    </div>
</template>

<script>
    export default {
        props: {
            width: String,
            fz: String,
            active: Boolean,
            content: String
        }
    }
</script>