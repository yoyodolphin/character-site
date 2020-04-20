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
        <router-link to="/">Home</router-link> |
        <router-link to="/about">About</router-link> |
        <router-link to="/Character">Character</router-link> |
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
    background-color: #777;
  }

  .logo{
    text-align: left;
    padding-left: 10px;
    font-size: 30px;
    float: left;

    a {
      font-weight: bold;
      color: #FFF;
    }
  }

@media screen and (max-width: 767px) {
#nav {
  display: none;
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
#nav {

  text-align: right;
  padding: 15px;

  a {
    font-weight: bold;
    color: #FFF;

    &.router-link-exact-active {
      color: #42b983;
    }
  }
}
}

</style>
