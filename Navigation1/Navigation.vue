<template>
  <div>
    <NavigationTop :mobileTitle="mobileTitle" :mainItem="mainItem" :menu="menu" @open-box="openBox()" />
    <div class="content" :class="{open : showUpdate}">
      <OpenBoxNav
        :menu="menu"
        @open-box="openBox()"
      />
    </div>
  </div>
</template>
<script>
import OpenBoxNav from "./OpenBoxNav";
import NavigationTop from "./NavigationTop";

export default {
  data() {
    return {
      showUpdate: true,
      open : "open",
      close: "close"
    };
  },

  props: {
    mobileTitle : {
      required: false
    },
    mainItem: {
      required: true,
    },
    menu: {
      required: true,
    },
  },

  components: {
    NavigationTop,
    OpenBoxNav,
  },

  methods: {
    openBox() {
      if (this.showUpdate == true) {
        this.showUpdate = false;
      } else if (this.showUpdate == false) {
        this.showUpdate = true;
      }
    },
  },
};
</script>

<style>
.showBox {
  display: none !important;
}

.open {
  transform: translateX(-768px);
}
@media screen and (min-width: 768px) {
  .open {
    transform: translateX(-2768px);
  }
}
.content {
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  transition: 1s transform cubic-bezier(.84,.23,.18,.76);
  z-index: 999;
}
</style>
