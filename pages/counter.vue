<template>
   <div class="counter">
    <h1>Counter</h1>
    <button class="text__red" v-on:click="decrement" :disabled="isDisabledDecrement">-</button>
    <span class="number" v-bind:class="{text__green: counterGreen, text__red: counterRed}">{{counter}}</span>
    <button class="text__green" v-on:click="increment" :disabled="isDisabledIncrement">+</button>
    <form v-on:submit.prevent="handlerSubmit">
        <label> Enter number
            <input class="input" type="number" min="0" max="20" v-on:input="handlerInput" :value="newCounter">
        </label>
    </form>
  </div>
</template>

<style>
    .number{
      font-weight: 700;
    }

    .counter{
        max-width: 1200px;
        margin: 0 auto;
        font-size: 28px;
        text-align: center;
    }

    .input{
        border-bottom: 4px solid tomato;
    }

    .text__red{
        color: red;
    }

    .text__green{
        color: green;
    }
    
    .text__red.text__green{
        color: brown;
    }
</style>

<script>
import Vue from "vuetify"
import Component from 'vue-class-component'
import { Watch } from 'vue-property-decorator'

@Component
export default class Header extends Vue {
  counter = 10
  newCounter = 0
  isDisabledDecrement = false
  isDisabledIncrement = false
  counterGreen = false
  counterRed = false

  @Watch('counter')
  counterDisabled(){
      if(this.counter > 19){
        this.isDisabledIncrement = true
    } else {
        this.isDisabledIncrement = false
    }

     if(this.counter < 1){
        this.isDisabledDecrement = true
    } else {
        this.isDisabledDecrement = false
    }

    this.counter % 3 === 0? this.counterRed = true : this.counterRed = false
    this.counter % 5 === 0? this.counterGreen = true : this.counterGreen = false
    if(!this.counter){
        this.counterRed = false
        this.counterGreen = false
    }
  }

  increment(){
    this.counter++
  }

  decrement() {
    this.counter--
  }

  handlerInput(e){
    this.newCounter = e.target.value
  }

  handlerSubmit(e){
    // e.preventDefault()
    this.counter = this.newCounter
    this.newCounter = 0
  }
}


</script>
