<template>
  <div class="App">
    <div class="App__apps-container">
      <TopBar />
      <Search />
      <Services />
      <!-- <div class="handlebar"></div>  -->
    </div>
    <div class="dissapearing">
    <Widget />
    <Card :title="cards[0].title" :about="cards[0].about" :source="cards[0].source" :sourceIcon="cards[0].sourceIcon" :cover="cards[0].cover" :date="cards[0].date"  />
    </div>
  </div>
</template>

<script>
import Services from '@/components/Services.vue';
import Card from '@/components/Card.vue';
import TopBar from '@/components/TopBar.vue';
import Search from '@/components/Search.vue';
import Widget from '@/components/Widget.vue';
import CoronaWidget from '@/components/CoronaWidget.vue';

export default {
  components: {
    Services, Card, TopBar, Search, Widget
  },
  data() {
    return {
      cards: [
        {
        title: 'Новая серия Рика и Морти',
        about: 'Чем «Рик и Морти» похожи на другие анимационные ситкомы, такие как «Симпсоны»..',
        source: 'Кинопоиск',
        sourceIcon: 'https://yastatic.net/s3/home/icons/services/mobile/kinopoisk_old.svg',
        cover: 'https://avatars.mds.yandex.net/get-kinopoisk-blog-post-thumb/40130/65f6d89f032e0ba113c81556cf09aae3/orig',
        date: 'Сегодня',
        }
      ]
    }
  },
    methods: {
    testMethod(event) {
      
      console.log(event);
      console.log(event.touches[0]);
      console.log(event.touches[0].clientY);
    // console.log(event);
    },
    increaseWidth(event) {

      let dissapearing = this.$el.getElementsByClassName('dissapearing')[0];
      let draggable = this.$el.getElementsByClassName('App__apps-container')[0];
      // console.log(dissapearing);
      // console.log(draggable);
      let handlePos = event.touches[0].clientY;
      let viewportHeight = event.view.innerHeight;

      let startFillRate = draggable.getBoundingClientRect().height * 100 / viewportHeight ;
      let opacity = Number(dissapearing.style.opacity);
      
      // высчитать какой % от шкалы текущее положение clientY
        let newfillRate = handlePos * 100 / viewportHeight;
        
      // присвоить это значение драггабл
        draggable.setAttribute("style",`height:${newfillRate}vh`);
      
      // привязать заполнение к опасити
        console.log(opacity);
        let newOpacity = opacity - 4 * (newfillRate-startFillRate)/100;
        console.log(newOpacity);
        dissapearing.setAttribute("style",`opacity: ${newOpacity}`);
  
      }
  },
  mounted() {
    this.$el.getElementsByClassName('App__apps-container')[0].addEventListener('touchmove', event => this.increaseWidth(event));
    }  
}
</script>

<style lang="scss">
.App {
//   margin: 0px;
//   padding: 20px;
  &__apps-container {
    background: #ffffff;
    padding: 0px 14px 24px 14px;
    border-radius: 0 0 24px 24px;
  }
}
.handlebar {
    width: 44px;
    height: 4px;
    border-radius: 16px;
    align-items: center;
    background-color: #F0F1F5;
}

</style>

