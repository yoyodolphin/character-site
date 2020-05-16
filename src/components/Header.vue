<template>
  <div class="header">
    <div class="inner">
      <div class="logo">
        <router-link to="/">yoyo's site</router-link>
      </div>
      <!-- スマホサイト用ナビ表示 -->
      <div class="mobile-nav">
        <div class="nav-toggle">
          <span></span>
          <span></span>
          <span></span>
        </div>
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
  height: 50px;
  background-color: #001726;
}

@media screen and (max-width: 767px) {
#nav {
  display: none;
}

.logo {
  padding-left: 10px;
  font-size: 30px;
  > a {
    font-weight: bold;
    color: #fff;
    text-decoration: none;
  }
}

.nav-toggle {
  width: 60px;
  height: 40px;
  position: absolute;
  right: 5px;
  top: 5px;
  background-color: #FFF;
  border: solid 1px;
}
}

@media screen and (min-width: 768px) {
a:hover {
  background-color: #004368;
  transition: .2s;
}
.inner {
  display: flex;
  justify-content: space-between;
  > .logo {
    padding-left: 10px;
    font-size: 30px;
    > a {
      font-weight: bold;
      color: #fff;
      text-decoration: none;
    }
  }
  > #nav {
    display: flex;
    height: 50px;
    > a {
      width: 120px;
      height: 50px;
      font-weight: bold;
      color: #FFF;
      padding: 15px 0;
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
