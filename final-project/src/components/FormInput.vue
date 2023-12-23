<template>
    <form @submit.prevent="sendContent">
        <text-input
            label="Username"
            validation="maximum 100 characters"
            placeholder="Daulet"
            id="username"
            @getContent="content => this.content.username = content"
        />
    
        <email-input 
            label="Email"
            placeholder="example@gmail.com"
            validation="input should contain '@'"
            id="email"
            @getContent="content => this.content.email = content"
        />

        <password-input 
            label="Password"
            validation="at least 4 charcters"
            id="password"
            @getContent="content => this.content.password = content"
        />

        <number-input 
            label="Phone"
            placeholder="8 (777) 777-7777"
            @getContent="content => this.content.phone = content"
        />

        <date-time-picker 
            label="Your Birthday"
            :time="false"
            @getContent="content => this.content.date = new Date(content)"
        />

        <label for="avatar">Avatar</label>
        <file-input 
            id="avatar"
            accept="image/*"
            @getContent="content => this.content.img = content"
        />

        <br>

        <span>
            <v-button :color="'#3535ff'">Submit</v-button>
        </span>
    </form>

</template>

<script>
    import TextInput from './Input/TextInput.vue';
    import DateTimePicker from './Input/DateTimePicker.vue';
    import FileInput from './Input/FileInput.vue';
    import NumberInput from './Input/NumberInput.vue';
    import PasswordInput from './Input/PasswordInput.vue';
    import EmailInput from './Input/EmailInput.vue';
    import VButton from './Buttons/VButton.vue';

    export default {
        data() {
            return {
                content: {
                    username: null,
                    email: null,
                    password: null,
                    phone: null,
                    date: null,
                    img: null,
                }
            }
        },
        components: {
            TextInput,
            DateTimePicker,
            FileInput,
            NumberInput,
            PasswordInput,
            EmailInput,
            VButton
        },
        methods: {
            sendContent() {
                this.$emit('getContent', this.content)
                console.log('Sent a content: ' + JSON.stringify(this.content))
            }
        },
        emits: ['getContent']
    }
</script>