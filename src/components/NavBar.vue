<template>
  <nav class="menu">
    <div>
      <router-link class="router-link" to="/">Меню</router-link>
    </div>
    <div>
      <router-link class="router-link" to="/liked"
        >Избранное ({{ itemsInLiked }})</router-link
      >
    </div>
    <div>
      <router-link class="router-link" to="/cart"
        >Корзина ({{ itemsInCart }})</router-link
      >
    </div>
  </nav>
</template>

<script>
import { mapGetters } from "vuex";

export default {
  name: "navBar",
  computed: {
    ...mapGetters(["itemsInCart", "itemsInLiked"]),
  },
};
</script>

<style scoped>
.menu {
  display: flex;
  justify-content: flex-end;
}
.menu > div {
  margin-right: 20px;
  margin-bottom: 20px;
}
.router-link {
  text-decoration: none;
  color: gray;
  border: 1px solid transparent;
  border-radius: 4px;
  padding: 10px;
}
.router-link:hover {
  color: rgb(145, 15, 15);
}
.router-link-exact-active {
  color: red;
  text-decoration-line: underline;
  text-decoration-skip-ink: none;
  text-underline-offset: 7px;
}
</style>
