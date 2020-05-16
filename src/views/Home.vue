<template>
  <div class="home">
    <b-carousel
      id="new-illust"
      v-model="slide"
      :interval="4000"
      indicators
      background="#999"
      img-width="1024"
      img-height="360"
      >
      <b-carousel-slide
        caption="New Illust First"
        img-blank>
        <p>ここに新着イラストを入れる</p>
      </b-carousel-slide>
      <b-carousel-slide
        caption="New Illust Second"
        img-blank>
        <p>ここに新着イラストを入れる</p>
      </b-carousel-slide>
      <b-carousel-slide
        caption="New Illust Third"
        img-blank>
        <p>ここに新着イラストを入れる</p>
      </b-carousel-slide>
    </b-carousel>
    <HelloWorld msg="Welcome to Your Vue.js App"/>
  </div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from '@/components/HelloWorld.vue';

export default {
  name: 'Home',
  components: {
    HelloWorld,
  },
};
</script>
