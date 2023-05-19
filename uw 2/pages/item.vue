<template>
  <div>
    <MainHeader />
    <ItemProductCard />
    <ItemDetalis />
    <ItemReviews />
    <ItemFeedback />
    <ItemWedding />
    <ItemCards />
    <MainFooter />
  </div>

</template>

<script>
import MainHeader from '../components/MainHeader.vue';
import ItemProductCard from '../components/ItemProductCard.vue'
import ItemDetalis from '../components/ItemDetalis.vue'
import ItemReviews from '../components/ItemReviews.vue'
import ItemFeedback from '../components/ItemFeedback.vue'
import ItemWedding from '../components/ItemWedding.vue'
import ItemCards from '../components/ItemCards.vue'
import MainFooter from '../components/MainFooter.vue'

export default {
    components: {
        MainHeader,
        ItemProductCard,
        ItemDetalis,
        ItemReviews,
        ItemFeedback,
        ItemWedding,
        ItemCards,
        MainFooter
    },
  name: 'ItemPage'
}
</script>