<template>
  <div>
    <h1>Welcome {{ user }}</h1>
    <button @click="logOut" class="btn">Log out</button>
    <p>
      <router-link
        :to="{
          name: 'invoices',
        }"
        >Invoices</router-link
      >
    </p>
  </div>
</template>

<script>
import store from "@/store.js";

export default {
  data() {
    return {
      user: store.user,
    };
  },
  methods: {
    logOut() {
      store.user = null;
      this.$router.push("/");
    },
  },
};
</script>
