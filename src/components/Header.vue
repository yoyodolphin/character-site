<template>
  <div class="header">
    <div class="inner">
      <div class="logo">
        <router-link to="/"><img class="sitesymbol" src="../assets/sitesymbol.png"></router-link>
      </div>
      <!-- スマホサイト用ナビ表示 -->
      <div class="mobile-nav">
        <label for="nav-menu">
          <div class="nav-button">
            <span></span>
            <span></span>
            <span></span>
          </div>
        </label>
        <input type="checkbox" id="nav-menu" name="listnav">
        <ul @click="clickLinkEve">
          <li><router-link to="/">Home</router-link></li>
          <li><router-link to="/about">About</router-link></li>
          <li><router-link to="/illust">Illust</router-link></li>
          <li><router-link to="/Character">Character</router-link></li>
          <li><router-link to="/Commission">Commission</router-link></li>
        </ul>
        <div class="nav-background mobile-nav" @click="clickLinkEve"></div>
      </div>

      <!-- PCサイト用ナビ表示 -->
      <div id="nav" class="global-nav">
        <router-link to="/">Home</router-link>
        <router-link to="/about">About</router-link>
        <router-link to="/illust">Illust</router-link>
        <router-link to="/Character">Character</router-link>
        <router-link to="/Commission">Commission</router-link>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Header',
  methods: {
    clickLinkEve() {
      const inputs = document.querySelector('input[type = "checkbox"]');
      inputs.checked = false;
    },
  },
};

</script>

<style scoped lang="scss">
.header {
  height: 70px;
  background-color: #001726;
  z-index: 5;
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
input {
  display: none;
}
.nav-background {
  width: 100vw;
  height: 100vh;
  position: fixed;
  display: none;
  background-color: #000;
}
.mobile-nav {
  position: absolute;
  top: 15px;
  right: 10px;
  > label {
    display: block;
    width: 40px;
    height: 40px;
    margin: 0;
    > .nav-button {
    width: 50px;
    height: 40px;
    position: absolute;
    display: flex;
    flex-direction: column;
    justify-content: space-around;
    right: 0;
    border: solid 1px #fff;
    border-radius: 3px;
    > span {
      width: 36px;
      height: 4px;
      margin: 0 auto;
      background-color: #fff;
    }
  }
  }
  ul {
    display: none;
    padding: 0;
    list-style: none;
    position: relative;
    background-color: #fff;
    border: 1px solid #d3d3d3;
    border-radius: 3px;
    z-index: 20;
    > li {
      width: 150px;
      height: 70px;
      line-height: 70px;
      border-bottom: 1px solid #d3d3d3;
    }
    > li:last-child {
      border-bottom: 0px;
    }
  }
  input:checked + ul{
    display: block;
    padding: 1rem;
  }
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
