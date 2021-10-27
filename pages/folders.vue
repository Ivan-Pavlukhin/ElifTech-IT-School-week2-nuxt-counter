<template>
   <div>
    <h1>folders</h1>
    <ul>
      <li v-for="item of structure" :key="item.title">
        <button v-if="item.folder" type="button">{{item.title}}</button>
        </li>
    </ul>
    <button v-on:click="handlerClickFolder">click</button>
  </div>
</template>

<script>
import Vue from "vuetify"
import Component from 'vue-class-component'

@Component
export default class Folders extends Vue {

 
}

</script>