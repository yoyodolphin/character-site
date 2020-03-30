<template>
  <div class="header">
    <div class="logo">
      <router-link to="/">yoyo's site</router-link>
    </div>
    <div id="nav">
      <router-link to="/">Home</router-link> |
      <router-link to="/about">About</router-link> |
      <router-link to="/Character">Character</router-link> |
      <router-link to="/Commission">Commission</router-link>
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
</style>
