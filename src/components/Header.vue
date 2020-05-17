<template>
  <div class="header">
    <div class="inner">
      <div class="logo">
        <router-link to="/"><img class="sitesymbol" src="../assets/sitesymbol.png"></router-link>
      </div>
      <!-- スマホサイト用ナビ表示 -->
      <div class="mobile-nav">
        <b-dropdown text="≡" size="lg" no-caret right>
          <b-dropdown-item><router-link to="/">Home</router-link></b-dropdown-item>
          <b-dropdown-divider></b-dropdown-divider>
          <b-dropdown-item><router-link to="/about">About</router-link></b-dropdown-item>
          <b-dropdown-divider></b-dropdown-divider>
          <b-dropdown-item><router-link to="/Character">Character</router-link></b-dropdown-item>
          <b-dropdown-divider></b-dropdown-divider>
          <b-dropdown-item><router-link to="/Commission">Commission</router-link></b-dropdown-item>
        </b-dropdown>
      </div>

      <!-- PCサイト用ナビ表示 -->
      <div id="nav" class="global-nav">
        <router-link to="/">Home</router-link>
        <router-link to="/about">About</router-link>
        <router-link to="/Character">Character</router-link>
        <router-link to="/Commission">Commission</router-link>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Header',
};
</script>

<style scoped lang="scss">
.header {
  height: 70px;
  background-color: #001726;
}
.sitesymbol {
  width: 60px;
  height: 60px;
}

@media screen and (max-width: 767px) {
#nav {
  display: none;
}

.logo {
  padding: 5px 0;
  font-size: 30px;
  > a {
    font-weight: bold;
    color: #fff;
    text-decoration: none;
  }
}

.mobile-nav {
  position: absolute;
  top: 10px;
  right: 10px;
}

}

@media screen and (min-width: 768px) {
.mobile-nav {
  display: none;
}
a:hover {
  background-color: #004368;
  transition: .2s;
}
.inner {
  display: flex;
  justify-content: space-between;
  > .logo {
    padding: 5px 10px;
    font-size: 30px;
    > a {
      font-weight: bold;
      color: #fff;
      text-decoration: none;
    }
  }
  > #nav {
    display: flex;
    height: 70px;
    > a {
      width: 120px;
      height: 70px;
      font-weight: bold;
      color: #FFF;
      padding: 22px 0;
      text-decoration: none;
      &.router-link-exact-active {
        color: #001726;
        background-color: #fff;
      }
    }
  }
}
}

</style>
