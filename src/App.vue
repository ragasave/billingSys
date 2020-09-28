<template>
  <div>
    <Nav :invoices="invoices"/>
    <div class="mx-auto pb-5 px-4 print-no-mt" style="margin-top: 100px;">
      <CreateBil :invoices="invoices"/>
    </div>
  </div>
</template>

<script>
// import CreateBil from './components/Create'
import CreateBil from './components/v2'
import Nav from './components/nav'
export default {
  name: 'App',
  created(){
    var invoices = window.localStorage.getItem('invoices');
    if(invoices){
      this.invoices = invoices;
      invoices = undefined;
    }
  },
  data(){
    return {
      invoices : []
    }
  },
  components: {
    CreateBil,
    Nav
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
