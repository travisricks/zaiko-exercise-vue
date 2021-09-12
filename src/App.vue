<template>
  <div class="d-grid gap-4 m-2 mt-4">
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
  name: "App",
  components: {
    CouponComponent,
    PremiumComponent,
    MenuComponent,
  },
};
</script>

<style lang="scss">
@import "~bootstrap/dist/css/bootstrap.css";

#app {
  font-family: "Noto Sans JP", Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  min-width: 275px;
  max-width: 750px;
  margin-left: auto;
  margin-right: auto;
  overflow-x: hidden;
  color: $color-text-dark;
}
</style>
