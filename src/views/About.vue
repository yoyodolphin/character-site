<template>
  <div class="about">
    <div class="profile">
      <h2>プロフィール</h2>
      <div class="profile-content">
        <img src="../assets/profile_image.jpg">
        <div class="profile-text">
          <h3>ヨーヨー / yoyo</h3>
          <p>ケモノや人外メインな絵描き。内容は主につるぷにやフェチ寄り(粘液、ラバーetc...)なイラストが多目。<br>
             ドラゴンや水棲生物、動物モチーフではない人外キャラなどが好き。
          <p>グッズ制作や着ぐるみなど、自由気ままにいろんな物に手を出しています。</p>
        </div>
      </div>
      <h2>リンク</h2>
      <div class="link-content">
        <ul>
          <li><i class="fas fa-parking fa-lg"></i><a href="https://www.pixiv.net/users/11095996" target="_blank">pixiv</a></li>
          <li><i class="fab fa-twitter-square fa-lg"></i><a href="https://twitter.com/yoyodol09" target="_blank">Twitter</a></li>
        </ul>
      </div>
    </div>
  </div>
</template>

<style scoped lang="scss">
@media screen and (max-width: 767px) {
.profile{
  > h2{
    margin: 30px 5vw;
    text-align: left;
    border-left: 6px solid;
    border-bottom: 2px solid;
    }
  > .profile-content{
    margin-bottom: 30px;
    > img{
      width: 60vw;
      height: 60vw;
      max-width: 200px;
      max-height: 200px;
      margin-bottom: 5vw;
      border: 1px solid;
    }
    > .profile-text{
      width: 90%;
      margin: 0 auto;
    }
  }
  > .link-content{
    text-align: left;
    padding-bottom: 30px;
    > ul{
      list-style: none;
      > li{
        padding: 3px 0;
        > i{
          padding-right: 10px;
        }
      }
    }
  }
}
}

@media screen and (min-width: 768px) {
.profile {
  width: 90vw;
  max-width: 900px;
  margin: 0 auto;
  > h2 {
    margin: 30px 0;
    text-align: left;
    border-left: 6px solid;
    border-bottom: 2px solid;
  }
  > .profile-content {
    display: flex;
    justify-content: center;
    margin-bottom: 50px;
    > img {
      width: 20vw;
      height: 20vw;
      border: 2px solid;
      margin-right: 50px;
      max-width: 200px;
      max-height: 200px;
    }
    > .profile-text {
      width: 70vw;
      text-align: left;
      }
    }
  > .link-content{
    text-align: left;
    padding-bottom: 30px;
    > ul{
      list-style: none;
      padding-left: 10px;
      > li{
        padding: 3px 0;
        > i{
        padding-right: 5px;
        }
      }
    }
  }
  }
}
</style>
