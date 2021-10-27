<template>
   <div>
    <ul class="list">
      <li class="li" v-for="day of week" :key="day">{{day}}</li>
    </ul>
    <main>
      <!-- <div class="container"><nuxt /></div> -->
    </main>
  </div>
</template>

<style>
  .list{
    width: 100%;
  }

  .li{
    margin-top: 15px;
    text-align: center;
    font-size: 28px;
    font-weight: 700;
    color: rgb(150, 240, 6);
  }

  .li:nth-child(2n){
    color: rgb(178, 39, 233);
  }

  .li:nth-child(3n){
    color: rgb(39, 68, 233);
  }


</style>

<script>
import Vue from "vuetify"
import Component from 'vue-class-component'

@Component
export default class Header extends Vue {
  week = [
    'Monday ', 'Tuesday', 'Wednesday', 'Thursday', 'Friday', 'Saturday', 'Sunday'
  ]
}
</script>
