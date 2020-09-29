<template>
  <div class="update-container d-flex flex-column justify-content-center">
    <div class="card shadow pt-2 pb-2 mt-5">
      <div class="card-body">
        <div
          @click="$emit('open-box')"
          class="d-flex justify-content-end mr-3 mt-1"
        >
          <i class="fas fa-times"></i>
        </div>
        <div class="navbar-collapse">
          <ul v-for="(item, index) in menu" :key="index" class="navbar-nav">
            <router-link
              tag="li"
              :to="'/' + item"
              class="d-flex justify-content-center items col-12"
              ><span @click="$emit('open-box')">{{ item }}</span></router-link
            >
          </ul>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    menu: {
      required: true,
    },
  },
};
</script>

<style scoped>
.card {
  min-width: 100%;
  height: 100vh;
  background-color: rgba(0, 0, 0, 0.8);
}

ul {
  list-style: none;
}
span {
  padding: 5px;
  border-bottom: 3px solid transparent;
  border-top: 3px solid transparent;
}
span:hover {
  animation: 1s border-bottom linear forwards, 1s border-top linear forwards, 1s border-sides linear forwards;
}
@keyframes border-bottom {
  from {
    border-bottom: 3px solid transparent;
  }
  to {
    border-bottom: 3px solid  rgba(74, 113, 74, 0.42);
    transform: scale(1.1,1.1)  ;
    text-shadow: 0.5px 0.5px;
    box-shadow: 6px 6px rgb(74, 113, 74);
  }
}
@keyframes border-sides {
  from {
    border-left: 3px solid transparent;
    border-right: 3px solid transparent;
  }
  to {
    border-left: 3px solid rgb(74, 113, 74);
    border-right: 3px solid  rgba(74, 113, 74, 0.42);

  }
}
@keyframes border-top {
  from {
    border-top: 3px solid transparent;
  }
  to {
    border-top: 3px solid rgb(74, 113, 74);
  }
}

.items {
  color: rgb(255, 255, 255) !important;
  font-size: 1rem;
  font-weight: bold;
  margin-bottom: 20px;
  cursor: pointer;
}

.items:hover {
  color: rgb(91, 139, 91) !important;
}

i {
  font-size: 2rem;
  color: white;
  padding: 10px;
  border-radius: 100px;
  margin-bottom: 20px;
  cursor: pointer;
}

i:hover {
  color: rgb(74, 113, 74);
}
</style>
