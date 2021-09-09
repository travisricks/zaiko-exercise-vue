<template>
  <div class="card m-2">
    <div class="card-body">
      <div class="text-center">
        <div class="spinner-border" role="status"></div>
      </div>

      <table class="table">
        <thead>
          <tr>
            <td>Item Name</td>
            <td>Price</td>
          </tr>
        </thead>
        <tbody>
          <tr class="table-info">
            <td>Cold Item</td>
            <td>¥000</td>
          </tr>
          <tr class="table-danger">
            <td>Hot Item</td>
            <td>¥000</td>
          </tr>
        </tbody>
      </table>
    </div>
  </div>
</template>

<script>
export default {
  name: 'MenuComponent',
}
</script>

<style lang="scss" scoped>
</style>
