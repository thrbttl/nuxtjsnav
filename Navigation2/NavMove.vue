<template>
  <header class="d-md-none bg-dark">
    <router-link to="/" tag="div" class="logo"
      ><img src="~/static/image/logo.png" width="30" alt="tahir battal"
    /></router-link>
    <router-link to="/" tag="h1" class="mr-0 ml-auto my-auto">{{
      mobileTitle
    }}</router-link>

    <button
      @click="toggleNav"
      class="nav-btn d-md-none d-block ml-auto"
      :aria-expanded="this.ariaExpanded"
      aria-controls="nav"
    >
      <span></span>
      <span></span>
      <span></span>
      <span class="sr">Menu</span>
    </button>
    <nav id="nav">
      <button
        @click="toggleNav"
        class="nav-close-btn d-flex justify-content-end"
      >
        <span></span>
        <span></span>
        <span class="sr">Close</span>
      </button>
      <ul>
        <li>
          <router-link tag="a" to="/" class="items"
            ><span @click="toggleNav">{{ mainItem }}</span>
          </router-link>
        </li>
        <li v-for="(item, index) in menu" :key="index">
          <router-link tag="a" :to="'/' + item" class="items">
            <span @click="toggleNav">{{ item }}</span>
          </router-link>
        </li>
      </ul>
    </nav>
  </header>
</template>

<script>
export default {
  data() {
    return {
      ariaExpanded: false,
    };
  },
  props: {
    mobileTitle: {
      required: true,
    },
    mainItem: {
      required: true,
    },
    menu: {
      required: true,
    },
  },
  methods: {
    toggleNav() {
      if (this.ariaExpanded == true) {
        this.ariaExpanded = false;
      } else if (this.ariaExpanded == false) {
        this.ariaExpanded = true;
      } else {
        log.error(err);
      }
    },
  },
};
</script>

<style scoped>
* {
  border: 0;
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}
header {
  box-shadow: 0 0 0.5em #0007;
  justify-content: space-between;
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  z-index: 0;
  display: flex;
  padding: 1.5em;
}

button {
  font: 1em Catamaran, sans-serif;
  line-height: 1.5;
}

nav {
  display: flex;
}

nav {
  justify-content: center;
  align-items: center;
  opacity: 0;
  position: fixed;
  top: 0;
  left: 0;
  visibility: hidden;
  transition: all 0.2s linear;
  width: 100%;
  height: 100%;
  z-index: 9;
}
nav ul,
h1,
h2,
.logo {
  font-size: 1.4em;
  line-height: 1;
}
nav a,
h1,
h2 {
  font-weight: bold;
}
nav ul {
  list-style: none;
  text-align: center;
}
nav li,
p {
  margin-bottom: 1.5rem;
}
h1 {
  color: #ffffff;
}
h2 {
  margin-bottom: 1em;
}
.logo {
  margin-right: 0.5rem;
}
.logo a:hover,
.logo a:focus {
  text-decoration: none;
}
.logo a:focus,
.nav-btn[aria-expanded="false"]:focus {
  filter: brightness(0.7);
  -webkit-filter: brightness(0.7);
}
.nav-close-btn:focus {
  opacity: 0.7;
}
.nav-btn,
.nav-close-btn {
  background: transparent;
  cursor: pointer;
  height: 1.5em;
}
.nav-btn {
  position: relative;
  width: 2em;
  z-index: 1;
}
.nav-btn span,
.nav-close-btn span {
  display: block;
  position: absolute;
  height: 0.25em;
  width: 100%;
  z-index: 2;
}
.nav-btn span {
  background: #ffffff;
  top: 0;
  right: 0;
  transition: all 0.2s 0.2s ease-out;
}
.nav-btn span:nth-of-type(2) {
  top: calc(50% - 0.125em);
  transition-delay: 0.4s;
}
.nav-btn span:nth-of-type(3) {
  top: calc(100% - 0.25em);
  transition-delay: 0.6s;
}
.nav-btn[aria-expanded="true"] span {
  top: -1.5em;
  right: -1.5em;
  height: 33.33vh;
  width: 100vw;
  transition-delay: 0.4s;
}
.nav-btn[aria-expanded="true"] span:nth-of-type(2) {
  top: calc(-1.5em + 33.33vh);
  transition-delay: 0.2s;
}
.nav-btn[aria-expanded="true"] span:nth-of-type(3) {
  top: calc(-1.5em + 66.67vh);
  transition-delay: 0s;
}
.nav-btn[aria-expanded="true"] ~ nav {
  opacity: 1;
  visibility: visible;
  transition: opacity 0.8s 0.8s ease-out;
}
.nav-close-btn {
  position: absolute;
  top: 1.5em;
  right: 1.5em;
  width: 1.5em;
}
.nav-close-btn span {
  background: #171717;
  top: 50%;
}

.nav-close-btn span:first-of-type {
  transform: translateY(-50%) rotate(-45deg);
}
.nav-close-btn span:nth-of-type(2) {
  transform: translateY(-50%) rotate(45deg);
}
.nav-btn span.sr,
.nav-close-btn span.sr {
  clip: rect(1px, 1px, 1px, 1px);
  overflow: hidden;
  width: 1px;
  height: 1px;
}

.items {
  padding: 5px;
  border-bottom: 3px solid transparent;
  border-top: 3px solid transparent;
  color: rgb(230, 230, 230) !important;
}
.items:hover {
  animation: 0.5s border-bottom ease-in forwards,
    0.5s border-top ease-in forwards, 0.5s border-sides linear forwards;
  color: rgb(255, 255, 255);
}
@keyframes border-bottom {
  from {
    border-bottom: 3px solid transparent;
  }
  to {
    border-bottom: 3px solid rgba(74, 113, 74, 0.42);
    transform: scale(1.1, 1.1);
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
    border-right: 3px solid rgba(74, 113, 74, 0.42);
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

@media screen and (prefers-color-scheme: dark) {
  nav a,
  nav a:active,
  nav a:visited {
    color: #f1f1f1;
  }

  a {
    color: #f45555;
    text-decoration: none;
  }
  a:active {
    color: #f22626;
  }
  a:visited {
    color: #f98686;
  }
  nav {
    background: #242424;
  }
  .nav-close-btn span {
    background: #ffffff;
  }
}
</style>
