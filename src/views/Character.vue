<template>
  <div class="character">
    <h1>My original characters</h1>
    <p>You can click links and see character sheets</p>
    <p>キャラクターの名前をクリックすると資料が閲覧できます。</p>
    <CharacterModal/>
    <CharacterList
      v-for="ch in chars"
      :key="ch.id"
      :ch="ch"
      @list-event="parentMethod"
      @send-id="getIndexMethod"
    />
    <CharacterModal
      :chm="chars"
      :val="parentData"
      :listid="modalIdNum"
      @modal-event="parentMethod"
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
          id: 0,
          url: require('@/assets/chara_helmue.png'), // eslint-disable-line global-require
          name: 'ヘルミュー',
          engname: 'Helmue',
          summary: `簡単な紹介文
二行目の説明`,
        },
        {
          id: 1,
          url: require('@/assets/chara_torot.png'), // eslint-disable-line global-require
          name: 'トロート',
          engname: 'Torot',
          summary: '',
        },
        {
          id: 2,
          url: require('@/assets/chara_bluebird.png'), // eslint-disable-line global-require
          name: 'ブルーバード',
          engname: 'Bluebird',
          summary: '',
        },
      ],
      parentData: 'true',
      modalIdNum: 0,
    }
  ),
  methods: {
    parentMethod(fromChildVal) {
      this.parentData = fromChildVal;
    },
    getIndexMethod(idNum) {
      this.modalIdNum = idNum;
    },
  },
};
</script>
