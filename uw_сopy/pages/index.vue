<template>
  <div>
    <MainHeader />
    <MainBanner />
    <MainCategory />
    <MainCards />
    <MainBody />
    <MainSubscribe /> 
    <MainNews />
    <MainFooter />
  </div>
</template>

<script>
import MainHeader from '../components/MainHeader.vue';
import MainBanner from '../components/MainBanner.vue';
import MainCategory from '../components/MainCategory.vue'
import MainCards from '../components/MainCards.vue';
import MainBody from '../components/MainBody.vue'
import MainSubscribe from '../components/MainSubscribe.vue';
import MainNews from '../components/MainNews.vue';
import MainFooter from '../components/MainFooter.vue'

export default {
  components: {
    MainHeader,
    MainBanner,
    MainCategory,
    MainCards,
    MainBody,
    MainSubscribe,
    MainNews, 
    MainFooter
  },
  name: 'IndexPage'
}
</script>
