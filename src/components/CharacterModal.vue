<template>
  <div class="cha-modal" v-bind:class="{ishidden: val}">
    <div class="cha-modal-back">
      <div class="cha-modal-window" v-bind:class="{ismove: val}">
        <div class="cha-modal-header">
          <b-button @click="triggerEvent">×</b-button>
        </div>
        <div class="cha-modal-content">
          <div class="chara-content-name">
            <h2>{{ chm[listid].name }}</h2>
            <p>{{ chm[listid].engname }}</p>
          </div>
          <div class="chara-content-image">
            <p>ここに立ち絵を表示</p>
          </div>
          <div class="chara-content-status">
            <p>性別：{{ gen[chm[listid].gender] }}</p>
            <p>誕生日：{{ chm[listid].birth[0] }}/{{ chm[listid].birth[1] }}</p>
            <p>種族：{{ families[chm[listid].family[0]] }} {{ families[chm[listid].family[1]] }}</p>
            <p>能力：{{ abi[chm[listid].ability[0]] }} {{ abi[chm[listid].ability[1]] }}</p>
          </div>
          <div class="chara-content-sentence">
            <p>{{ chm[listid].summary }}</p>
          </div>
        </div>
        <div class="cha-modal-footer">
          <b-button @click="triggerEvent">閉じる</b-button>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped lang="scss">
.cha-modal {
  transition: opacity 200ms;
}
.ishidden {
  opacity: 0;
  pointer-events: none;
}
.ismove{
  transform: translateY(-100px);
}
.cha-modal-back {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-color: rgba(0,0,0,0.5);
  z-index: 1;
  > .cha-modal-window{
    width: 96vw;
    height: 96vh;
    margin: 2vh 2vw;
    background-color: #fff;
    transition: all 500ms 0ms ease;
    border-radius: 5px;
    overflow-y: auto;
    z-index: 2;
    > .cha-modal-header {
      text-align: right;
    }
    > .cha-modal-content {
      text-align: left;
      > .chara-content-name {
        > h2 {
          margin: 0 3vw;
        }
        > p {
          margin: 0 3vw;
          padding-bottom: 10px;
          border-bottom: 1px solid;
        }
      }
      > .chara-content-image {
        width: 90vw;
        height: 300px;
        margin: 10px 3vw;
        border: 1px solid;
      }
      > .chara-content-status {
        margin: 0 3vw;
        > p {
          border-bottom: 1px dotted;
        }
      }
      > .chara-content-sentence {
        padding-top: 10px;
        border-top: 1px solid;
        margin: 0 3vw;
        white-space: pre-wrap;
        word-wrap: break-word;
      }
    }
    > .cha-modal-footer {
      margin: 5px 0;
    }
  }
}

/* タブレット用表示 */
@media screen and (min-width: 768px) and (max-width: 1024px) {
.cha-modal-back {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-color: rgba(0,0,0,0.5);
  z-index: 1;
  > .cha-modal-window{
    width: 650px;
    height: 96vh;
    margin: 2vh auto;
    background-color: #fff;
    transition: all 500ms 0ms ease;
    border-radius: 5px;
    overflow-y: auto;
    z-index: 2;
    > .cha-modal-header {
      text-align: right;
    }
    > .cha-modal-content {
      text-align: left;
      > .chara-content-name {
        > h2 {
          margin: 0 3vw;
        }
        > p {
          margin: 0 3vw;
          padding-bottom: 10px;
          border-bottom: 1px solid;
        }
      }
      > .chara-content-image {
        width: 600px;
        height: 300px;
        margin: 10px auto;
        border: 1px solid;
      }
      > .chara-content-status {
        margin: 0 3vw;
        > p {
          border-bottom: 1px dotted;
        }
      }
      > .chara-content-sentence {
        padding-top: 10px;
        border-top: 1px solid;
        margin: 0 3vw;
      }
    }
    > .cha-modal-footer {
      margin: 5px 0;
    }
  }
}
}

/* PC用表示 */
@media screen and (min-width: 1024px){
.cha-modal-back {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-color: rgba(0,0,0,0.5);
  z-index: 1;
  > .cha-modal-window{
    width: 800px;
    height: 96vh;
    margin: 2vh auto;
    background-color: #fff;
    transition: all 500ms 0ms ease;
    border-radius: 5px;
    overflow-y: auto;
    z-index: 2;
    > .cha-modal-header {
      text-align: right;
    }
    > .cha-modal-content {
      text-align: left;
      > .chara-content-name {
        margin-bottom: 30px;
        > h2 {
          margin: 0 3vw;
        }
        > p {
          margin: 0 3vw;
          padding-bottom: 10px;
          border-bottom: 1px solid;
        }
      }
      > .chara-content-image {
        width: 600px;
        height: 600px;
        margin: 10px auto;
        border: 1px solid;
      }
      > .chara-content-status {
        display: flex;
        flex-wrap: wrap;
        justify-content: space-between;
        margin: 0 3vw;
        > p {
          border-bottom: 1px dotted;
          width: 35vw;
          margin: 10px 0;
        }
      }
      > .chara-content-sentence {
        padding-top: 10px;
        border-top: 1px solid;
        margin: 20px 3vw 0 3vw;
      }
    }
    > .cha-modal-footer {
      margin: 5px 0;
    }
  }
}
}
</style>

<script type="text/javascript">
export default {
  name: 'CharacterModal',
  props: {
    chm: {
      type: Array,
      required: true,
    },
    val: {
      type: [Boolean, String],
    },
    listid: {
      type: Number,
    },
    families: {
      type: Object,
    },
    abi: {
      type: Object,
    },
    gen: {
      type: Object,
    },
  },
  methods: {
    triggerEvent() {
      const elements = document.body;
      elements.classList.remove('modal-active');
      this.$emit('modal-event', true);
    },
  },
};
</script>
