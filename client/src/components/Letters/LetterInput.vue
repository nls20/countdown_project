<template>
    <section>
        <button @click="addConsonant">Consonant</button>
        <button @click="addVowel">Vowel</button>
  </section>
</template>

<script>
import {eventBus} from '@/main.js'

    export default {
        name: 'letter-input',
        data(){
            return {
                letterToAdd: "letters",
                consonants: ['b','b', 'c', 'c', 'd', 'd', 'd', 'd', 'f', 'f', 'g', 'g', 'g', 'g', 'h', 'h', 'j', 'k', 'l', 'l', 'l', 'l', 'l', 'm', 'm', 'm', 'n', 'n', 'n', 'n', 'n', 'p', 'p', 'p', 'q', 'r', 's', 't', 'r', 's', 't', 'r', 's', 't', 'r', 's', 't', 'v', 'w', 'w', 'x', 'y', 'y', 'z'],
                vowels: ['a', 'e', 'a', 'e', 'a', 'e', 'a', 'e', 'i', 'i', 'i', 'o', 'o', 'o', 'u', 'u']
            }
        },
        methods:{
            addConsonant(){
                this.letterToAdd = this.consonants[Math.floor(Math.random() * this.consonants.length)]
                this.sendEventBus()
            },
            addVowel(){
                this.letterToAdd = this.vowels[Math.floor(Math.random() * this.vowels.length)]
                this.sendEventBus()
            },
            sendEventBus(){
                eventBus.$emit('add-letter', this.letterToAdd)
                
            }
        }
    }
</script>

<style lang="css" scoped>
button {
    box-shadow:inset 0px 1px 0px 0px #97c4fe;
	background:linear-gradient(to bottom, #3d94f6 5%, #1e62d0 100%);
	background-color:#3d94f6;
	border-radius:6px;
	border:1px solid #337fed;
	display:inline-block;
	cursor:pointer;
	color:#ffffff;
	font-family:Arial;
	font-size:large;
	font-weight:bold;
	padding:6px 24px;
	text-decoration:none;
	text-shadow:0px 1px 0px #1570cd;
    margin: 20px 40px;
    width: 180px;
    height: 100px
}


section {
    display: grid;
    justify-items: center;
    grid-template-columns: 1fr 1fr;
}
</style>


const randomElement = consonant[Math.floor(Math.random() * consonant.length)];