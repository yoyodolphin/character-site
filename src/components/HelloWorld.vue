<template>
  <div class="hello">
    <div class="home-content">
      <div class="home-summary">
        <p>サイトの概要</p>
      </div>
      <p>ヨーヨーが個人で運営しているウェブサイトです。<br>
      主に一次創作のギャラリーやキャラクター紹介、コミッションの受付情報などを掲載しています。</p>
      <div class="home-information">
        <div class="home-news">
          <p>更新履歴</p>
        </div>
        <div class="home-twitter-widget">
          <p>ツイッターウィジェット</p>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped lang="scss">
.home-content {
  margin: 50px 5vw;
  > p {
    padding-bottom: 50px;
    border-bottom: 1px solid;
  }
  > .home-summary {
    > p {
      width: 200px;
      height: 50px;
      margin: 0 auto;
      vertical-align: middle;
      border: 1px dotted;
    }
  }
  > .home-information {
    display: flex;
    justify-content: space-around;
    margin-top: 50px;
    > .home-news {
      width: 40vw;
      height: 300px;
      border: 1px solid;
    }
    > .home-twitter-widget{
      width: 40vw;
      height: 300px;
      border: 1px solid;
    }
  }
}
</style>

<script>
export default {
  name: 'HelloWorld',
  props: {
    msg: String,
  },
};
</script>
