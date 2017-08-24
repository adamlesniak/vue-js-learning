<template>
  <div class="row">
    <app-quote @click.native="deleteQuote" v-for="quote in quotes">{{ quote }}</app-quote>
  </div>
</template>

<script>
  import Quote from './Quote.vue';

  export default {
    props: ['quotes'],
    components: {
      appQuote: Quote
    },
    methods: {
      deleteQuote() {
        alert('yo');
      }
    }
  }
</script>

<style>
</style>
