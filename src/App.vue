<template>
  <CouponComponent />
  <PremiumComponent />
  <MenuComponent />
</template>

<script>
import CouponComponent from "./components/CouponComponent";
import PremiumComponent from "./components/PremiumComponent";
import MenuComponent from "./components/MenuComponent";

export default {
  name: 'App',
  components: {
    CouponComponent,
    PremiumComponent,
    MenuComponent,
  }
}
</script>

<style>
@import '~bootstrap/dist/css/bootstrap.css';

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  max-width: 960px;
  margin: auto;
}
</style>
