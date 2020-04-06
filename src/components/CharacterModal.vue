<template>
<<<<<<< Updated upstream
  <div class="overlay">
    <div class="modal">
      <div class="modal-header">
      </div>
      <div class="modal-content">
        <h1>{{ chr.name }}</h1>
        <p>ここにキャラクターのプロフィールを載せる</p>
      </div>
      <div class="modal-footer">
        <b-button>閉じる</b-button>
=======
  <div class="cha-modal" v-bind:class="{ishidden: val}">
    <div class="cha-modal-back">
      <div class="cha-modal-window" v-bind:class="{ismove: val}">
        <div class="cha-modal-header">
          <b-button>×</b-button>
        </div>
        <div class="cha-modal-content">
          <h2>{{ chm.name }}</h2>
          <p>{{ chm.engname }}</p>
          <p>性別や誕生日</p>
        </div>
        <div class="cha-modal-footer">
          <b-button @click="triggerEvent">閉じる</b-button>
        </div>
>>>>>>> Stashed changes
      </div>
    </div>
  </div>
</template>

<style scoped lang="scss">
<<<<<<< Updated upstream
.overlay {
  display: flex;
  align-items: center;
  justify-content: center;
  z-index: 1;
=======
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
>>>>>>> Stashed changes
  position: fixed;
  top: 0;
  left: 0;
  width: 100vw;
  height: 100vw;
  background-color: rgba(0,0,0,0.5);
<<<<<<< Updated upstream
  > .modal{
    z-index: 2;
    width: 70vw;
    padding: 1em;
    background: #fff;
=======
  z-index: 1;
  > .cha-modal-window{
    width: 80vw;
    margin: 5vw auto;
    background-color: #fff;
    transition: all 500ms 0ms ease;
    > .cha-modal-header {
      text-align: right;
    }
>>>>>>> Stashed changes
  }
}
</style>

<script type="text/javascript">
export default {
  name: 'CharacterModal',
  props: {
<<<<<<< Updated upstream
    chr: {
      type: Object,
=======
    chm: {
      type: Array,
>>>>>>> Stashed changes
      required: true,
    },
    val: {
      type: Boolean,
    },
  },
  data: () => (
    {
      parentData: true,
    }
  ),
  methods: {
    triggerEvent() {
      this.$emit('child-event', true);
    },
  },
};
</script>
