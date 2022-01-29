<template>
  <div>
    <Header />
    <Mainpart />
  </div>
</template>

<script>
import Header from './components/Header';
import Mainpart from './components/Mainpart';
export default {
  name: 'App',
  components: {
      Header,
      Mainpart
  }
}
</script>

<style>
*{
  box-sizing: border-box;
}
</style>
