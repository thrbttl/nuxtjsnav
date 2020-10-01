<template>
  <div>
    <nav class="navbar navbar-expand-md navbar-dark fixed-top bg-dark">
      <!-- <router-link tag="a" to="/" class="navbar-brand ml-3 mr-5">
      <img src="../image/logo.png" width="30" alt="tahir battal" /> *Your src path required
    </router-link> -->
    <router-link tag="a" to="/" class="navbar-brand d-md-block d-none">{{mainItem}}</router-link>
      <div class="collapse navbar-collapse" id="navbarCollapse">
        <ul v-for="(item, index) in menu" :key="index" class="navbar-nav">
          <router-link tag="li" :to="'/' + item" class="nav-item">
            <span class="nav-link">{{ item }} </span>
          </router-link>
        </ul>
      </div>
      <button @click="$emit('open-box')" class="btn btn-light d-md-none">
        <i class="fas fa-bars"></i>
      </button>
    </nav>
  </div>
</template>

<script>
export default {
  props: {
    mainItem: {
      required: true,
    },
    menu: {
      required: true,
    },
  },
};
</script>
<style scoped>
.nav-link {
  cursor: pointer !important;
}
</style>