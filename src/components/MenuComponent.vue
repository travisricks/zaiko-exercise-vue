<template>
  <div class="card m-2">
    <div class="card-body">
      <template v-if="!isLoading && !hasAxiosError">
        <div class="dropdown text-end">
          <button
            class="bg-green [ btn btn-success btn-sm dropdown-toggle ]"
            type="button"
            id="dropdownMenuButton"
            data-bs-toggle="dropdown"
            aria-expanded="false"
          >
            {{ dropdownLabel }}
          </button>
          <ul
            class="dropdown-menu dropdown-menu-end"
            aria-labelledby="dropdownMenuButton"
          >
            <li
              class="dropdown-item"
              @click="handleSort(sortPriceLowHigh, 'Price: Low to High')"
            >
              Price: Low to High
            </li>
            <li
              class="dropdown-item"
              @click="handleSort(sortPriceHighLow, 'Price: High to Low')"
            >
              Price: High to Low
            </li>
            <li
              class="dropdown-item"
              @click="handleSort(sortAlphabetical, 'Alphabetical')"
            >
              Alphabetical
            </li>
            <li class="dropdown-item" @click="handleSort(sortType, 'Type')">
              Type
            </li>
            <li><hr class="dropdown-divider" /></li>

            <li class="dropdown-item" @click="handleSort(items, 'Sort')">
              Reset Sort
            </li>
            <li class="dropdown-item" @click="hasAxiosError = true">
              Simulate API Error
            </li>
          </ul>
        </div>
      </template>
      <div v-if="hasAxiosError">
        <p>
          申し訳ありませんが、現在この情報を取得することができませんので、後ほどもう一度お試しください。
        </p>
        <p>
          <a class="link-success" @click="hasAxiosError = false"
            >エラーをリセットする (reset error)</a
          >
        </p>
      </div>
      <template v-else>
        <div v-if="isLoading" class="text-center">
          <div class="spinner-border" role="status"></div>
        </div>
        <table v-else class="table table-sm table-hover">
          <caption class="visually-hidden">
            List of drinks
          </caption>
          <thead>
            <tr>
              <th scope="col">Item Name</th>
              <th scope="col">Price</th>
            </tr>
          </thead>
          <tbody>
            <tr
              v-for="{ name, category, price, id } in displayedItems"
              :key="id"
              :class="{
                'table-info': category === 'Iced',
                'table-danger': category === 'Hot',
              }"
            >
              <td>{{ name }}</td>
              <td>￥{{ Number(price).toLocaleString() }}</td>
            </tr>
          </tbody>
        </table>
      </template>
    </div>
  </div>
</template>

<script>
import axios from "axios";
export default {
  name: "MenuComponent",
  data() {
    return {
      items: null,
      isLoading: true,
      hasAxiosError: false,
      displayedItems: null,
      dropdownLabel: "Sort",
    };
  },
  computed: {
    sortPriceLowHigh() {
      const temp = [...this.items];
      return temp.sort((a, b) => (a.price > b.price ? 1 : -1));
    },
    sortPriceHighLow() {
      const temp = [...this.items];
      return temp.sort((a, b) => (a.price < b.price ? 1 : -1));
    },
    sortAlphabetical() {
      const temp = [...this.items];
      return temp.sort((a, b) => (a.name > b.name ? 1 : -1));
    },
    sortType() {
      const temp = [...this.items];
      return temp.sort((a, b) => (a.category < b.category ? 1 : -1));
    },
  },
  methods: {
    handleSort(type, label) {
      this.displayedItems = type;
      this.dropdownLabel = label;
    },
  },
  mounted() {
    axios
      .get(
        process.env.VUE_APP_API_PATH || "http://localhost:8080/data/menu.json"
      )
      .then((response) => {
        this.items = response.data.items;
        this.displayedItems = response.data.items;
      })
      .catch((error) => {
        console.error(error);
        this.hasAxiosError = true;
      })
      .finally(() => {
        // setTimeout is for demo to simulate waiting for server. 
        // This would not be used in a real application.
        setTimeout(() => {
          this.isLoading = false;
        }, 500);
      });
  },
};
</script>

<style lang="scss" scoped>
.dropdown-item {
  &:active {
    background-color: $color-green-dark;
  }
  &:hover {
    cursor: pointer;
  }
}
.link-success {
  cursor: pointer;
}
.card {
  @include borderPink;
}
.bg-green {
  background-color: $color-green-dark;
}
</style>
