<template>
  <div>
    <NavMove :mobileTitle="mobileTitle" :mainItem="mainItem" :menu="menu"/>
    <NavigationTop class="d-md-block d-none" :mainItem="mainItem" :menu="menu"/>
  </div>
</template>

<script>
import NavMove from "./NavMove";
import NavigationTop from './NavigationTop'

export default {
  props: {
    mobileTitle:{
      required: true
    },
    mainItem: {
      required: true,
    },
    menu: {
      required: true,
    },
  },
  components: {
    NavMove,
    NavigationTop
  },
};
</script>

