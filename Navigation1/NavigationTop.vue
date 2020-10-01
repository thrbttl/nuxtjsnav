<template>
  <div>
    <nav class="navbar navbar-expand-md navbar-dark fixed-top bg-dark">
      <router-link tag="a" to="/" class="navbar-brand ml-3 mr-5">
        <img src="~/static/image/logo.png" width="30" alt="tahir battal" />
      </router-link>
      <router-link tag="a" to="/" class="navbar-brand d-md-block d-none">{{
        mainItem
      }}</router-link>
      <div class="collapse navbar-collapse" id="navbarCollapse">
        <ul v-for="(item, index) in menu" :key="index" class="navbar-nav">
          <router-link tag="li" :to="'/' + item" class="nav-item">
            <span class="nav-link">{{ item }} </span>
          </router-link>
        </ul>
      </div>
      <h3 class="d-md-none text-white text-capitalize my-auto mr-5">{{mobileTitle}}</h3>
      <button @click="$emit('open-box')" class="btn btn-light d-md-none">
        <span></span>
        <span></span>
        <span></span>
      </button>
    </nav>
  </div>
</template>

<script>
export default {
  props: {
    mobileTitle:{
      required : false
    },
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

.btn {
  background-color: transparent;
  padding: 0;
  margin: 0;
  cursor: pointer;
  height: 1.5em;
  width: 2em;
  position: relative;
  z-index: 1;
  border: none;
}

.btn span {
  background: #ffffff;
  top: 0;
  right: 5px;
  display: block;
  position: absolute;
  height: 0.25em;
  width: 100%;
  z-index: 2;
}
.btn span:nth-of-type(2) {
  top: calc(50% - 0.125em);
}
.btn span:nth-of-type(3) {
  top: calc(100% - 0.25em);
}
</style>
