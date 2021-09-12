<template>
  <div class="wrapper">
    <CouponComponent :amount="1000" />
    <PremiumComponent />
    <MenuComponent />
  </div>
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

<style lang="scss">
@import '~bootstrap/dist/css/bootstrap.css';

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  max-width: 750px;
  margin-left: auto;
  margin-right: auto;
  overflow-x: hidden;
  color: $color-text-dark;
}

.wrapper {
  & > * + * {
    margin-top: 2rem !important; // !important to override bootstrap
  }
}
</style>
