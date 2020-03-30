<template>
  <div class="character">
    <h1>My original characters</h1>
    <p>You can click links and see character sheets</p>
    <p>キャラクターの名前をクリックすると資料が閲覧できます。</p>
    <CharacterList
      v-for="ch in chars"
      :key="ch.name"
      :ch="ch"
    />
  </div>
</template>

<style scoped lang="scss">
</style>

<script type="text/javascript">
import CharacterList from '@/components/CharacterList.vue';

export default {
  name: 'Character',
  components: {
    CharacterList,
  },
  data: () => (
    {
      chars: [
        {
          url: require('@/assets/caImage1.png'), // eslint-disable-line global-require
          name: 'ヘルミュー',
          engname: 'Helmue',
          summary: '簡単な紹介文',
        },
        {
          url: require('@/assets/caImage2.png'), // eslint-disable-line global-require
          name: 'トロート',
          engname: 'Torot',
          summary: '',
        },
        {
          url: require('@/assets/caImage3.png'), // eslint-disable-line global-require
          name: 'ブルーバード',
          engname: 'Bluebird',
          summary: '',
        },
        {
          url: '',
          name: 'ペリドート',
          engname: 'Peridort',
          summary: '',
        },
        {
          url: '',
          name: 'ポリエス',
          engname: 'Polies',
          summary: '',
        },
      ],
    }
  ),
};
</script>
