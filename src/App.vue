<template>
  <div id="app">
    <Autocomplete :items="customers"
      filterby="name"
      @change="onChange"
      title="Look for a customer"
      @selected="customerSelected"/>
  </div>
</template>

<script>
import customers from './assets/customers';
import Autocomplete from './components/Autocomplete'

export default {
  name: 'App',
  mounted() {
    this.customers = customers;
  },
  data() {
    return {
      customers: []
    };
  },
  methods: {
    customerSelected(customer) {
      console.log(`Customer Selected:\nid: ${customer.id}\nname: ${customer.name}`);
    },
    onChange(value) {
      // do something with the current value
    }
  },
  components: {
    Autocomplete
  }
}
</script>

<style>
#app {
  margin: 0px auto;
  margin-top: 60px;
  width: 400px;
}
</style>
