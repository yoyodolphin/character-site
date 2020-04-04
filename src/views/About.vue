<template>
  <div class="about">
    <div class="profile">
      <h1>プロフィール</h1>
        <div class="profile-content">
          <img src="../assets/profileImage.jpg">
          <div class="profile-text">
            <h2>ヨーヨー / yoyo</h2>
            <p>ケモノや人外メインな絵描き。つるぷにやフェチ寄り(粘液、ラバーetc...)なイラストが多目。<br>
               グッズ制作や着ぐるみなど、自由気ままにいろんな物に手を出しています。
            </p>
          </div>
        </div>
      </div>
  </div>
</template>

<style scoped lang="scss">
.profile{
  width: 90vw;
  margin: 5vw 5vw;
  background-color: #fff;
  > h1{
    margin-bottom: 5vw;
    text-align: left;
    border-left: 6px solid;
    border-bottom: 2px solid;
  }
  > .profile-content {
    display: flex;
    justify-content: center;
    > .profile-text{
      text-align: left;
      margin-left: 5vw;
      }
    }
  }
img {
      width: 15vw;
      height: 15vw;
      border: 2px solid;
    }
</style>
