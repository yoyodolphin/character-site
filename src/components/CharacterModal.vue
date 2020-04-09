<template>
  <div class="cha-modal" v-bind:class="{ishidden: val}">
    <div class="cha-modal-back">
      <div class="cha-modal-window" v-bind:class="{ismove: val}">
        <div class="cha-modal-header">
          <b-button>×</b-button>
        </div>
        <div class="cha-modal-content">
          <h2>{{ chm[listid].name }}</h2>
          <p>{{ chm[listid].engname }}</p>
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
  width: 100vw;
  height: 100vw;
  background-color: rgba(0,0,0,0.5);
  z-index: 1;
  > .cha-modal-window{
    width: 80vw;
    margin: 5vw auto;
    background-color: #fff;
    transition: all 500ms 0ms ease;
    > .cha-modal-header {
      text-align: right;
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
  },
  methods: {
    triggerEvent() {
      this.$emit('modal-event', true);
    },
  },
};
</script>
