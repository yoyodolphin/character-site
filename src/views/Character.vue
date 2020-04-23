<template>
  <div class="character">
    <h2>キャラ一覧</h2>
    <p class="summury">各キャラクターのアイコンをクリックすると詳細が閲覧できます。</p>
    <div class="chara-list-col">
    <CharacterList
      class="chara-list-content"
      v-for="ch in chars"
      :key="ch.id"
      :ch="ch"
      @list-event="parentMethod"
      @send-id="getIndexMethod"
    />
    </div>
    <CharacterModal
      :chm="chars"
      :val="parentData"
      :listid="modalIdNum"
      @modal-event="parentMethod"
    />
  </div>
</template>

<style scoped lang="scss">
h2 {
  margin: 5vw 5vw 0 5vw;
  text-align: left;
  border-left: 6px solid;
  border-bottom: 2px solid;
}
.summury {
  padding: 30px 0;
  margin: 0 5vw 5vw 5vw;
  border-bottom: 1px solid;
}

.chara-list-col{
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  width: 90vw;
  margin: 0 5vw;
  > .chara-list-content{
    margin: 0 2vw;
  }
}
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
          url: require('@/assets/chara_pald.png'), // eslint-disable-line global-require
          name: 'パルド',
          engname: 'Pald',
          summary: `みんなの保護者的立場の温厚なドラゴン。
真面目でやることはやる性格、しかしそんな性格とは裏腹に丸呑み癖がついている。

体はゼリーのような質感で少しひんやりしている。そのため自身より小さい子であれば簡単に体内に収めることができる。

服装の大きいファスナーはおしゃれの一環であるため実際に使うことはできない。`,
        },
        {
          id: 1,
          url: require('@/assets/chara_pisnol.png'), // eslint-disable-line global-require
          name: 'ピスノル',
          engname: 'Pisnol',
          summary: '',
        },
        {
          id: 2,
          url: require('@/assets/no-image.png'), // eslint-disable-line global-require
          name: 'プレテリット',
          engname: 'Preterit',
          summary: '',
        },
        {
          id: 3,
          url: require('@/assets/no-image.png'), // eslint-disable-line global-require
          name: 'ペリドート',
          engname: 'Peridort',
          summury: '',
        },
        {
          id: 4,
          url: require('@/assets/no-image.png'), // eslint-disable-line global-require
          name: 'ポリエス',
          engname: 'Polies',
          summury: '',
        },
        {
          id: 5,
          url: require('@/assets/no-image.png'), // eslint-disable-line global-require
          name: 'シャルボ',
          engname: 'Shalbo',
          summury: '',
        },
        {
          id: 6,
          url: require('@/assets/no-image.png'), // eslint-disable-line global-require
          name: 'スウェイム',
          engname: 'Sweim',
          summury: '',
        },
        {
          id: 7,
          url: require('@/assets/no-image.png'), // eslint-disable-line global-require
          name: 'ヨウト',
          engname: 'Yoto',
          summury: '',
        },
        {
          id: 8,
          url: require('@/assets/no-image.png'), // eslint-disable-line global-require
          name: 'ミヅキ',
          engname: 'Mizuki',
          summury: '',
        },
        {
          id: 9,
          url: require('@/assets/no-image.png'), // eslint-disable-line global-require
          name: 'アクー',
          engname: 'Aqoo',
          summury: '',
        },
        {
          id: 10,
          url: require('@/assets/no-image.png'), // eslint-disable-line global-require
          name: 'オンタ',
          engname: 'Onta',
          summury: '',
        },
        {
          id: 11,
          url: require('@/assets/no-image.png'), // eslint-disable-line global-require
          name: 'セルメト',
          engname: 'Selmet',
          summury: '',
        },
        {
          id: 12,
          url: require('@/assets/no-image.png'), // eslint-disable-line global-require
          name: 'ユークル',
          engname: 'Eucl',
          summury: '',
        },
        {
          id: 13,
          url: require('@/assets/no-image.png'), // eslint-disable-line global-require
          name: 'クーペ',
          engname: 'Qoope',
          summury: '',
        },
        {
          id: 14,
          url: require('@/assets/no-image.png'), // eslint-disable-line global-require
          name: 'ベルブ',
          engname: 'Belb',
          summury: '',
        },
        {
          id: 15,
          url: require('@/assets/no-image.png'), // eslint-disable-line global-require
          name: 'ロトープ',
          engname: 'Rotope',
          summury: '',
        },
        {
          id: 16,
          url: require('@/assets/chara_helmue.png'), // eslint-disable-line global-require
          name: 'ヘルミュー',
          engname: 'Helmue',
          summury: '',
        },
        {
          id: 17,
          url: require('@/assets/no-image.png'), // eslint-disable-line global-require
          name: 'エズ',
          engname: 'Ez',
          summury: '',
        },
        {
          id: 18,
          url: require('@/assets/chara_torot.png'), // eslint-disable-line global-require
          name: 'トロート',
          engname: 'Torot',
          summury: '',
        },
        {
          id: 19,
          url: require('@/assets/no-image.png'), // eslint-disable-line global-require
          name: 'マグック',
          engname: 'Magck',
          summury: '',
        },
        {
          id: 20,
          url: require('@/assets/no-image.png'), // eslint-disable-line global-require
          name: 'メルツ',
          engname: 'Melts',
          summury: '',
        },
        {
          id: 21,
          url: require('@/assets/no-image.png'), // eslint-disable-line global-require
          name: 'サクア・ヘイル',
          engname: 'Xacooa・hail',
          summury: '',
        },
        {
          id: 22,
          url: require('@/assets/no-image.png'), // eslint-disable-line global-require
          name: '???',
          engname: '???',
          summury: '',
        },
        {
          id: 23,
          url: require('@/assets/no-image.png'), // eslint-disable-line global-require
          name: 'レスクーラ',
          engname: 'RESCoRa',
          summury: '',
        },
        {
          id: 24,
          url: require('@/assets/no-image.png'), // eslint-disable-line global-require
          name: 'チッチー',
          engname: 'Chichee',
          summury: '',
        },
        {
          id: 25,
          url: require('@/assets/no-image.png'), // eslint-disable-line global-require
          name: 'ルコ・ペスカトール',
          engname: 'Lco・pescatore',
          summury: '',
        },
        {
          id: 26,
          url: require('@/assets/no-image.png'), // eslint-disable-line global-require
          name: 'ニヌイス',
          engname: 'Ninuis',
          summury: '',
        },
        {
          id: 27,
          url: require('@/assets/no-image.png'), // eslint-disable-line global-require
          name: '???',
          engname: '???',
          summury: '',
        },
        {
          id: 28,
          url: require('@/assets/no-image.png'), // eslint-disable-line global-require
          name: '???',
          engname: '???',
          summury: '',
        },
        {
          id: 29,
          url: require('@/assets/no-image.png'), // eslint-disable-line global-require
          name: 'カイラル・アマルガム',
          engname: 'Chiral・amalgam',
          summury: '',
        },
        {
          id: 30,
          url: require('@/assets/no-image.png'), // eslint-disable-line global-require
          name: 'ノシュア',
          engname: 'Noshea',
          summury: '',
        },
        {
          id: 31,
          url: require('@/assets/no-image.png'), // eslint-disable-line global-require
          name: 'ネリュッタ',
          engname: 'Neluetta',
          summury: '',
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
      const elements = document.body;
      elements.classList.add('modal-active');
      this.modalIdNum = idNum;
    },
  },
};
</script>
