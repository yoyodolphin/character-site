<template>
  <div class="footer">
    <div class="footer-content">
      <div class="footer-link">
        <a href="https://www.pixiv.net/users/11095996">pixiv</a>
        <a href="https://twitter.com/yoyodol09">Twitter</a>
      </div>
      <p>2020 yoyo</p>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Footer',
};
</script>

<style scoped lang="scss">
.footer {
  display: flex;
  align-items: center;
  justify-content: center;
  height: 80px;
  color: #fff;
  background-color: #001726;
  > .footer-content {
    > .footer-link {
      > a {
        margin: 0 10px;
        color: #fff;
      }
    }
  }
}
</style>
