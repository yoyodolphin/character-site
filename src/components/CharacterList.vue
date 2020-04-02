<template>
  <div>
    <div class="chara-list">
      <div class="left-col">
        <img class="chara-img" :src="ch.url">
      </div>
      <div class="right-col">
        <div class="name">
          <div class="chara-name">{{ ch.name }}</div>
          <div class="eng-chara-name">{{ ch.engname }}</div>
        </div>
        <p class="summary">{{ ch.summary }}</p>
      </div>
    </div>
  </div>
</template>

<style scoped lang="scss">
.chara-list{
  display: flex;
  margin: 10px auto;
  width: 90vw;
  height: 20vw;
  transition: .5s;
  cursor: pointer;
  > .left-col {
    display: inline-block;
    width: 20vw;
    height: 20vw;
    background-color: #00b8ff;
    > .chara-img{
      max-width: 20vw;
      max-height: 20vw;
    }
  }
  > .right-col {
    display: inline-block;
    width: 70vw;
    height: 20vw;
    border: 1px solid #000080;
    text-align: left;
    > .name {
      display: flex;
      justify-content: flex-start;
      align-items: center;
      margin: 10px;
      color: #696969;
      border-bottom: 1px dashed;
      > .chara-name{
      font-size: 5vw;
      }
      > .eng-chara-name {
        margin-left: 2vw;
        font-size: 3vw;
        color: #c0c0c0;
      }
    }
    > .summary{
      margin: 0 10px;
      white-space: pre-wrap;
      word-wrap: break-word;
    }
  }
}

.chara-list:hover{
  opacity: 0.5;
}
</style>

<script type="text/javascript">
export default {
  name: 'CharacterList',
  props: {
    ch: {
      type: Object,
      required: true,
    },
  },
};
</script>
