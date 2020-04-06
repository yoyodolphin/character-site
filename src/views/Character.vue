<template>
  <div class="character">
    <h1>My original characters</h1>
    <p>You can click links and see character sheets</p>
    <p>キャラクターの名前をクリックすると資料が閲覧できます。</p>
<<<<<<< Updated upstream
    <p v-if="showContent">あああああ</p>
    <b-button @click="openModal">on</b-button>
    <b-button @click="closeModal">off</b-button>
=======
>>>>>>> Stashed changes
    <CharacterList
      v-for="ch in chars"
      :key="ch.name"
      :ch="ch"
<<<<<<< Updated upstream
      @click="openModal"
    />
    <CharacterModal
      :chr="chr"
=======
      @child-list-event="parentMethod"
    />
    <CharacterModal
      :chm="chars"
      :val="parentData"
      @child-event="parentMethod"
>>>>>>> Stashed changes
    />
  </div>
</template>

<style scoped lang="scss">
</style>

<script type="text/javascript">
import CharacterList from '@/components/CharacterList.vue';
import CharacterModal from '@/components/CharacterModal.vue';

export default {
  name: 'Character',
  components: {
    CharacterList,
    CharacterModal,
  },
  data: () => (
    {
      chars: [
        {
          url: require('@/assets/chara_helmue.png'), // eslint-disable-line global-require
          name: 'ヘルミュー',
          engname: 'Helmue',
          summary: `簡単な紹介文
二行目の説明`,
        },
        {
          url: require('@/assets/chara_torot.png'), // eslint-disable-line global-require
          name: 'トロート',
          engname: 'Torot',
          summary: '',
        },
        {
          url: require('@/assets/chara_bluebird.png'), // eslint-disable-line global-require
          name: 'ブルーバード',
          engname: 'Bluebird',
          summary: '',
        },
      ],
<<<<<<< Updated upstream
      showContent: false,
    }
  ),
  openModal: () => {
    this.showContent = true;
  },
  closeModal: () => {
    this.showContent = false;
=======
      parentData: 'true',
    }
  ),
  methods: {
    parentMethod(fromChildVal) {
      this.parentData = fromChildVal;
    },
>>>>>>> Stashed changes
  },
};
</script>
