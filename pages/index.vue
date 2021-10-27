<template>
   <div>
    <h1>Components</h1>
    <main>
      <!-- <div class="container"><nuxt /></div> -->
    </main>
  </div>
</template>

<script>
import Vue  from 'vuetify'
import Component from 'vue-class-component'

@Component
export default class Counter extends Vue {
  title = 'counter'
}

</script>