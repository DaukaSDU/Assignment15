<template>
    <label class="input-file">
	   	<span class="input-file-text" type="text">{{ file.name }}</span>
	   	<input type="file" name="file" :id="id" :accept="accept" @change="handleFile">        
 	   	<span class="input-file-btn">
            <svg xmlns="http://www.w3.org/2000/svg" height="16" width="16" viewBox="0 0 512 512">
                <path d="M288 109.3V352c0 17.7-14.3 32-32 32s-32-14.3-32-32V109.3l-73.4 73.4c-12.5 
                12.5-32.8 12.5-45.3 0s-12.5-32.8 0-45.3l128-128c12.5-12.5 32.8-12.5 45.3 0l128 
                128c12.5 12.5 12.5 32.8 0 45.3s-32.8 12.5-45.3 0L288 109.3zM64 352H192c0 35.3 28.7 
                64 64 64s64-28.7 64-64H448c35.3 0 64 28.7 64 64v32c0 35.3-28.7 64-64 64H64c-35.3 
                0-64-28.7-64-64V416c0-35.3 28.7-64 64-64zM432 456a24 24 0 1 0 0-48 24 24 0 1 0 0 48z"/>
            </svg>
        </span>
 	</label>
</template>

<script>
    export default {
        data() {
            return {
                file: ''
            }
        },
        methods: {
            handleFile(event) {
                const fileInput = event.target
                const files = fileInput.files

                if (files.length > 0) {
                    const chosenFile = files[0]
                    console.log('Chosen file: ' + chosenFile.name)
                    this.file = chosenFile
                }
                this.sendContent()
            },
            sendContent() {
                this.$emit('getContent', this.file)
            }
        },
        props: {
			accept: String,
			id: String
        },
        emits: ['getContent']
    }
</script>

<style>
.input-file {
	position: relative;
	display: inline-block;
}
.input-file-text {
	padding: 0 10px;
	line-height: 40px;
	text-align: left;
	height: 40px;
	display: block;
	float: left;
	box-sizing: border-box;
	width: 200px;
	border-radius: 6px 0px 0 6px;
	border: 1px solid #ddd;
    overflow: hidden;
}
.input-file-btn {
    position: relative;
	display: inline-block;
	cursor: pointer;
	outline: none;
	text-decoration: none;
	font-size: 14px;
	vertical-align: middle;
	color: rgb(255 255 255);
	text-align: center;
	border-radius: 0 4px 4px 0;
	background-color: #5e5eff;
	line-height: 22px;
	height: 40px;
	padding: 10px 20px;
	box-sizing: border-box;
	border: none;
	margin: 0;
	transition: background-color 0.2s;
}
.input-file-btn svg {
    fill: #fff;
}
.input-file input[type=file] {
	position: absolute;
	z-index: -1;
	opacity: 0;
	display: block;
	width: 0;
	height: 0;
}
 
/* Focus */
.input-file input[type=file]:focus + .input-file-btn {
	box-shadow: 0 0 0 0.2rem rgba(0,123,255,.25);
}
 
/* Hover/active */
.input-file:hover .input-file-btn {
	background-color: #7878ff;
}
.input-file:active .input-file-btn {
	background-color: #3535ff;
}
 
/* Disabled */
.input-file input[type=file]:disabled + .input-file-btn {
	background-color: #eee;
}
</style>