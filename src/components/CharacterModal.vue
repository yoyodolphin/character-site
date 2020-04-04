<template>
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
      </div>
    </div>
  </div>
</template>

<style scoped lang="scss">
.overlay {
  display: flex;
  align-items: center;
  justify-content: center;
  z-index: 1;
  position: fixed;
  top: 0;
  left: 0;
  width: 100vw;
  height: 100vw;
  background-color: rgba(0,0,0,0.5);
  > .modal{
    z-index: 2;
    width: 70vw;
    padding: 1em;
    background: #fff;
  }
}
</style>

<script type="text/javascript">
export default {
  name: 'CharacterModal',
  props: {
    chr: {
      type: Object,
      required: true,
    },
  },
};
</script>
