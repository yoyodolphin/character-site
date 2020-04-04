<template>
  <div class="modal">
    <h1>キャラクター名</h1>
  </div>
</template>

<style scoped lang="scss">
.modal {
  width: 100%;
  height: 100%;
  background: #000;
}
</style>

<script type="text/javascript">
export default {
  name: 'CharacterModal',
  props: {
    ch: {
      type: Object,
      required: true,
    },
  },
};
</script>
