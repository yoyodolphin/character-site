<template>
  <div>
    <div @click="sendEvent">
      <div class="chara-list" @click="triggerEvent">
        <div class="chara-image">
          <img :src="ch.url">
        </div>
        <div class="chara-name">
          <p>{{ ch.name }}</p>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped lang="scss">
.chara-list {
  margin: 10px auto;
  width: 150px;
  height: 200px;
  transition: .5s;
  cursor: pointer;
  > .chara-image {
    display: inline-block;
    max-width: 150px;
    max-height: 150px;
    > img {
      max-width: 150px;
      max-height: 150px;
      border-radius: 50%;
      border: solid 3px #000038;
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
  methods: {
    triggerEvent() {
      const scrollReset = document.getElementsByClassName('cha-modal-window')[0];
      scrollReset.scrollTop = 0;
      this.$emit('list-event', false);
    },
    sendEvent() {
      this.$emit('send-id', this.ch.id);
    },
  },
};
</script>
