<template>
  <div class="character">
    <h2>キャラ一覧</h2>
    <p class="summary">各キャラクターのアイコンをクリックすると詳細が閲覧できます。</p>
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
      :families="family"
      :abi="ability"
      :gen="gender"
      :val="parentData"
      :listid="modalIdNum"
      @modal-event="parentMethod"
    />
  </div>
</template>

<style scoped lang="scss">
.character {
  width: 90vw;
  max-width: 900px;
  margin: 0 auto 70px auto;
}

h2 {
  margin: 30px 5vw 10px;
  text-align: left;
  border-left: 6px solid;
  border-bottom: 2px solid;
}
.summary {
  padding: 30px 0;
  margin: 0 5vw 5vw 5vw;
  border-bottom: 1px solid;
}

.chara-list-col{
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
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
      gender: {
        0: '------',
        1: '♂',
        2: '♀',
        3: '♂♀',
      },
      family: {
        0: '',
        1: 'ドラゴン',
        2: 'イルカ',
        3: 'スライム',
        4: 'フウセン',
        5: 'ゴースト',
        6: 'サメ',
        7: 'ウサギ',
        8: 'キツネ',
        9: 'クラゲ',
        10: 'ヤギ',
        11: 'ウナギ',
        12: 'クリオネ',
        13: 'シャチ',
        14: 'ロボット',
        15: 'トカゲ',
        16: 'カエル',
        99: '------',
      },
      ability: {
        0: '',
        1: '融解',
        2: '丸呑み',
        3: '膨張',
        4: '粘液まみれ',
        5: 'TF',
        6: 'TS',
        7: '風船化',
        8: '同族化',
        9: 'ぬいぐるみ化',
        10: 'ヘドロ化',
        11: '催眠、洗脳',
        12: '取り込み',
        13: '銃撃',
        14: '固め',
        15: '電気',
        16: '火炎',
        17: '浮遊',
        18: '拘束',
        99: '------',
      },
      chars: [
        {
          id: 0,
          url: require('@/assets/chara_pald.png'), // eslint-disable-line global-require
          name: 'パルド',
          engname: 'Pald',
          gender: 1,
          birth: [5, 24],
          family: [1, 0],
          ability: [2, 8],
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
          gender: 1,
          birth: [3, 16],
          family: [2, 1],
          ability: [1, 0],
          summary: `ドラゴン種のイルカの子。
泳ぎは大の得意で水中を約50km/hで進むことができる。地上での運動は平均的。
ゴーグルを使用するとさらに早く泳げるようになる。

他者とのコミュニケーションが苦手であまり表情を見せることはない。本人もそのことで日々悩んでいるらしい。`,
        },
        {
          id: 2,
          url: require('@/assets/chara_preterit.png'), // eslint-disable-line global-require
          name: 'プレテリット',
          engname: 'Preterit',
          gender: 1,
          birth: [1, 6],
          family: [1, 0],
          ability: [99, 0],
          summary: `暢気でマイペースな性格。
日々眠たそうな顔をしているが別に睡眠不足というわけではない。

甘いものと時計が好きで、よく時計をいじったり自作したりと器用な一面もある。
甘いものをつい食べ過ぎてしまう癖があり、そのことによる体重増加を少し気にしている。`,
        },
        {
          id: 3,
          url: require('@/assets/no-image.png'), // eslint-disable-line global-require
          name: 'ペリドート',
          engname: 'Peridort',
          gender: 1,
          birth: [8, 23],
          family: [2, 0],
          ability: [17, 0],
          summary: `水兵イルカ。
どんな時でも明るく前向きでムードメーカーの役割を担っている。

ある程度の高さなら空中を飛ぶことができる。しかし泳ぎはあまり得意ではない。`,
        },
        {
          id: 4,
          url: require('@/assets/no-image.png'), // eslint-disable-line global-require
          name: 'ポリエス',
          engname: 'Polies',
          gender: 0,
          birth: [9, 8],
          family: [3, 0],
          ability: [1, 11],
          summary: `ポジティブな性格のスライムドラゴン
体の小ささを駆使して素早く飛び跳ねたり壁を張ったりして移動する。

抱きついた相手の体をスライム化させることができ、その体に入り込んで意のままに操ることができる。`,
        },
        {
          id: 5,
          url: require('@/assets/no-image.png'), // eslint-disable-line global-require
          name: 'シャルボ',
          engname: 'Shalbo',
          gender: 1,
          birth: [11, 8],
          family: [6, 1],
          ability: [2, 0],
          summary: '',
        },
        {
          id: 6,
          url: require('@/assets/no-image.png'), // eslint-disable-line global-require
          name: 'スウェイム',
          engname: 'Sweim',
          gender: 1,
          birth: [7, 14],
          family: [7, 4],
          ability: [7, 3],
          summary: '',
        },
        {
          id: 7,
          url: require('@/assets/no-image.png'), // eslint-disable-line global-require
          name: 'ヨウト',
          engname: 'Yoto',
          gender: 1,
          birth: [2, 20],
          family: [8, 0],
          ability: [99, 0],
          summary: '',
        },
        {
          id: 8,
          url: require('@/assets/no-image.png'), // eslint-disable-line global-require
          name: 'ミヅキ',
          engname: 'Mizuki',
          gender: 1,
          birth: [3, 30],
          family: [1, 2],
          ability: [13, 18],
          summary: '',
        },
        {
          id: 9,
          url: require('@/assets/no-image.png'), // eslint-disable-line global-require
          name: 'アクー',
          engname: 'Aqoo',
          gender: 1,
          birth: [4, 9],
          family: [9, 0],
          ability: [18, 0],
          summary: '',
        },
        {
          id: 10,
          url: require('@/assets/no-image.png'), // eslint-disable-line global-require
          name: 'オンタ',
          engname: 'Onta',
          gender: 1,
          birth: [4, 27],
          family: [10, 0],
          ability: [11, 0],
          summary: '',
        },
        {
          id: 11,
          url: require('@/assets/no-image.png'), // eslint-disable-line global-require
          name: 'セルメト',
          engname: 'Selmet',
          gender: 0,
          birth: [7, 31],
          family: [1, 3],
          ability: [2, 1],
          summary: '',
        },
        {
          id: 12,
          url: require('@/assets/no-image.png'), // eslint-disable-line global-require
          name: 'ユークル',
          engname: 'Eucl',
          gender: 1,
          birth: [8, 23],
          family: [1, 0],
          ability: [99, 0],
          summary: '',
        },
        {
          id: 13,
          url: require('@/assets/no-image.png'), // eslint-disable-line global-require
          name: 'クーペ',
          engname: 'Qoope',
          gender: 1,
          birth: [10, 22],
          family: [1, 0],
          ability: [13, 5],
          summary: '',
        },
        {
          id: 14,
          url: require('@/assets/no-image.png'), // eslint-disable-line global-require
          name: 'ベルブ',
          engname: 'Belb',
          gender: 0,
          birth: [12, 3],
          family: [5, 0],
          ability: [18, 8],
          summary: '',
        },
        {
          id: 15,
          url: require('@/assets/no-image.png'), // eslint-disable-line global-require
          name: 'ロトープ',
          engname: 'Rotope',
          gender: 1,
          birth: [3, 17],
          family: [99, 0],
          ability: [11, 0],
          summary: '',
        },
        {
          id: 16,
          url: require('@/assets/chara_helmue.png'), // eslint-disable-line global-require
          name: 'ヘルミュー',
          engname: 'Helmue',
          gender: 2,
          birth: [4, 23],
          family: [1, 0],
          ability: [9, 0],
          summary: '',
        },
        {
          id: 17,
          url: require('@/assets/no-image.png'), // eslint-disable-line global-require
          name: 'エズ',
          engname: 'Ez',
          gender: 1,
          birth: [5, 20],
          family: [11, 3],
          ability: [12, 1],
          summary: '',
        },
        {
          id: 18,
          url: require('@/assets/chara_torot.png'), // eslint-disable-line global-require
          name: 'トロート',
          engname: 'Torot',
          gender: 1,
          birth: [7, 30],
          family: [1, 12],
          ability: [2, 4],
          summary: '',
        },
        {
          id: 19,
          url: require('@/assets/no-image.png'), // eslint-disable-line global-require
          name: 'マグック',
          engname: 'Magck',
          gender: 1,
          birth: [10, 1],
          family: [13, 0],
          ability: [99, 0],
          summary: '',
        },
        {
          id: 20,
          url: require('@/assets/no-image.png'), // eslint-disable-line global-require
          name: 'メルツ',
          engname: 'Melts',
          gender: 0,
          birth: [10, 30],
          family: [5, 0],
          ability: [1, 18],
          summary: '',
        },
        {
          id: 21,
          url: require('@/assets/no-image.png'), // eslint-disable-line global-require
          name: 'サクア・ヘイル',
          engname: 'Xacooa・hail',
          gender: 1,
          birth: [12, 15],
          family: [1, 0],
          ability: [99, 0],
          summary: '',
        },
        {
          id: 22,
          url: require('@/assets/no-image.png'), // eslint-disable-line global-require
          name: '???',
          engname: '???',
          gender: 3,
          birth: [2, 26],
          family: [1, 0],
          ability: [2, 6],
          summary: '',
        },
        {
          id: 23,
          url: require('@/assets/no-image.png'), // eslint-disable-line global-require
          name: 'レスクーラ',
          engname: 'RESCoRa',
          gender: 0,
          birth: [3, 8],
          family: [14, 0],
          ability: [15, 0],
          summary: '',
        },
        {
          id: 24,
          url: require('@/assets/no-image.png'), // eslint-disable-line global-require
          name: 'チッチー',
          engname: 'Chichee',
          gender: 1,
          birth: [5, 27],
          family: [1, 0],
          ability: [12, 8],
          summary: '',
        },
        {
          id: 25,
          url: require('@/assets/no-image.png'), // eslint-disable-line global-require
          name: 'ルコ・ペスカトール',
          engname: 'Lco・pescatore',
          gender: 1,
          birth: [7, 22],
          family: [2, 0],
          ability: [99, 0],
          summary: '',
        },
        {
          id: 26,
          url: require('@/assets/no-image.png'), // eslint-disable-line global-require
          name: 'ニヌイス',
          engname: 'Ninuis',
          gender: 1,
          birth: [10, 23],
          family: [5, 0],
          ability: [11, 17],
          summary: '',
        },
        {
          id: 27,
          url: require('@/assets/no-image.png'), // eslint-disable-line global-require
          name: '???',
          engname: '???',
          gender: 0,
          birth: [11, 3],
          family: [15, 4],
          ability: [7, 3],
          summary: '',
        },
        {
          id: 28,
          url: require('@/assets/no-image.png'), // eslint-disable-line global-require
          name: '???',
          engname: '???',
          gender: 1,
          birth: [8, 22],
          family: [99, 0],
          ability: [10, 0],
          summary: '',
        },
        {
          id: 29,
          url: require('@/assets/no-image.png'), // eslint-disable-line global-require
          name: 'カイラル・アマルガム',
          engname: 'Chiral・amalgam',
          gender: 1,
          birth: [11, 26],
          family: [1, 0],
          ability: [1, 8],
          summary: '',
        },
        {
          id: 30,
          url: require('@/assets/no-image.png'), // eslint-disable-line global-require
          name: 'ノシュア',
          engname: 'Noshea',
          gender: 1,
          birth: [2, 6],
          family: [1, 0],
          ability: [15, 0],
          summary: '',
        },
        {
          id: 31,
          url: require('@/assets/no-image.png'), // eslint-disable-line global-require
          name: 'ネリュッタ',
          engname: 'Neluetta',
          gender: 1,
          birth: [5, 6],
          family: [1, 0],
          ability: [2, 4],
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
      const elements = document.body;
      elements.classList.add('modal-active');
      this.modalIdNum = idNum;
    },
  },
};
</script>
