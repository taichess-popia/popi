<template>
  <header class="header-component std-padding">
    <div>
      <img src="~/assets/images/logo.svg" />
    </div>
    <div>
      <ul class="nav-list">
        <li><a href="#home">Home</a></li>
        <li><a href="#features">Features</a></li>
        <li><a href="#partner">Partner</a></li>
        <li><a href="#contact">Contact</a></li>
      </ul>
      <button class="hamburger">
        <div></div>
        <div></div>
        <div></div>
      </button>
      <div class="sidebar">
        <ul class="flex-column flex-center">
          <li><a href="#home" class="white-text">Home</a></li>
          <li><a href="#features" class="white-text">Features</a></li>
          <li><a href="#partner" class="white-text">Partner</a></li>
          <li><a href="#contact" class="white-text">Contact</a></li>
        </ul>
      </div>
    </div>
  </header>
</template>

<script>
export default {
  data() {
    return {
      sidebarOpen: false
    };
  }
};
</script>

<style lang="scss" scoped>
@import "../assets/css/partials/_variables.scss";
@import "../assets/css/partials/_mixins.scss";

.sidebar {
  background-color: $dark-blue;
  width: 90vw;
  height: 100vh;
  padding-top: 1.5rem;
  top: 0;
  position: absolute;
  right: -90vw;
  transition-duration: 0.2s;
}

a {
  text-decoration: none;
}

header.header-component {
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  background-color: #fff;
  padding-top: 1.5rem;
  padding-bottom: 1.5rem;
  display: flex;
  justify-content: space-between;
  align-items: center;
  box-shadow: 0 -5px 10px $dark-blue;
}

ul {
  list-style-type: none;
  padding: 0;
}

ul.nav-list {
  display: flex;
  justify-content: space-around;
  align-items: center;
  display: none;
  @include breakpoint($medium) {
    display: flex;
  }
}

ul.nav-list > li {
  margin: 0 1rem;
}

.hamburger {
  background-color: transparent;
  border: 0;
  display: block;
  @include breakpoint($medium) {
    display: none;
  }

  &:focus {
    outline: none;

    + .sidebar {
      right: 0;
    }
  }

  > * {
    width: 25px;
    height: 5px;
    border-radius: 999px;
    background-color: $dark-blue;
  }
  > * + * {
    margin-top: 3px;
  }
}
</style>
