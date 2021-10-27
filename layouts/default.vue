<template>
  <div>
    <ul class="header">
      <li class="item" v-for="(value, key) in list" :key="key"><NuxtLink exact-active-class="active" class="link" v-bind:to="value">{{key}}</NuxtLink></li>
    </ul>
    <nuxt />
  </div>
</template>

<style>
  .header{
    display: flex;
  }

  .item{
    margin-left: 40px;
    list-style-type: none;
    font-size: 20px;
    font-weight: 700;
  }

  .link{
    text-decoration: none;
    color: rgb(21, 104, 230)
  }

  .active{
    color: rgb(44, 240, 26)
  }
</style>

<script>
import Vue  from 'vuetify'
import Component from 'vue-class-component'

@Component
export default class Header extends Vue {
  list = {
    folders: "/folders",
    array: "/array",
    counter: "/counter"
  }
}

</script>