<template>
  <div class="home">
    <div class="home-image">
      <img src="../assets/homeimage.png">
      <div class="word-image">
        <p class="word-fir">Be smooth. Be shiny.</p>
        <p class="word-sec">Dive into another world!</p>
      </div>
    </div>
    <div class="home-content">
      <div class="home-summary">
        <div>サイトの概要</div>
        <p>ヨーヨーが個人で運営しているウェブサイトです。<br>
           現在は主にキャラクター紹介、コミッションの受付情報などを掲載しています。</p>
      </div>
      <details>
        <summary>更新履歴</summary>
          <p>1/1 webサイト公開</p>
      </details>
    </div>
  </div>
</template>

<style scoped lang="scss">
p{
  margin: 0;
}

/*スマホ用表示*/
@media screen and (max-width: 767px) {
.home-image {
  width: 100%;
  height: 200px;
  > img {
    width: 100%;
    height: 200px;
    object-fit: cover;
    object-position: 50% 10%;
  }
  > .word-image {
    font-size: 20pt;
    position: relative;
    right: 5px;
    bottom: 80px;
    text-align: right;
    z-index: 1;
    > .word-fir {
      color: #fff;
    }
    > .word-sec {
      font-weight: bold;
      color: #fff;
    }
  }
}

.home-content {
  margin: 30px 5vw;
  > .home-summary {
    width: 100%;
    padding-bottom: 20px;
    border-bottom: 1px solid;
    > div {
      border: 1px dotted;
      padding: 10px 5px;
      margin: 0 20vw 20px 20vw;
    }
  }
  > details {
    margin-top: 20px;
    > summary {
      border: 1px dotted;
      padding: 10px 5px;
      margin: 20px 20vw;
    }
  }
}
}

/*PC用表示*/
@media screen and (min-width: 768px) {
.home-image {
  width: 100%;
  height: 400px;
  > img {
    width: 100%;
    height: 400px;
    object-fit: cover;
    object-position: 50% 10%;
  }
  > .word-image {
    font-size: 30pt;
    position: relative;
    right: 5px;
    bottom: 120px;
    text-align: right;
    > .word-fir {
      color: #fff;
    }
    > .word-sec {
      font-weight: bold;
      color: #fff;
    }
  }
}

.home-content {
  margin: 30px auto;
  width: 90vw;
  max-width: 900px;
  text-align: center;
  > .home-summary {
    padding-bottom: 50px;
    border-bottom: 1px solid;
    > div {
      border: 1px dotted;
      padding: 10px 5px;
      margin: 0 30% 50px 30%;
    }
  }
  > details {
    margin: 30px 0 100px 0;
    > summary {
      border: 1px dotted;
      padding: 10px 0;
      margin: 20px 40%;
    }
  }
}
}

</style>

<script>
</script>
