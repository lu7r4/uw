<template>

    <div v-if="isMobileScreen">
        <div class="wrapper">
            <div class="reviews-title">отзывы</div>
            <div class="review-block">
                <div class="reviews">
                    <div v-for="(review, index) in reviews" :key="index" class="review">
                        <div class="user-info">
                            <img :src="review.avatar" alt="User Avatar">
                            <div class="user-name">
                                    <span>{{ review.name }}</span>
                                </div>
                        </div>
                        <div class="review-content">
                            <div class="name-rating">
    
                                <div class="rating">
                                    <span v-for="star in review.rating" :key="star" class="star"><img src="../assets/icons/rating_add.png" alt="rating_add"></span>
                                    <div class="date">{{ review.date }}</div>
                                
                                </div>
                            </div>
                        <div class="text">{{ review.text }}</div>
                        </div>
                    </div>
                </div>
                <div class="images">
                    <img src="../assets/images/review/review_1.png" alt="review_1">
                    <img src="../assets/images/review/review_2.png" alt="review_2">
                </div>
            </div>
        </div>
    
    </div>
    
    <div v-else>
    <div class="item-reviews">
        <div class="wrapper">
            <div class="reviews-title">отзывы</div>
            <div class="review-block">
                <div class="reviews">
                    <div v-for="(review, index) in reviews" :key="index" class="review">
                        <div class="user-info">
                            <img :src="review.avatar" alt="User Avatar">
                        </div>
                        <div class="review-content">
                            <div class="name-rating">
                                <div class="user-name">
                                    <span>{{ review.name }}</span>
                                </div>
                                <div class="rating">
                                    <span v-for="star in review.rating" :key="star" class="star"><img src="../assets/icons/rating_add.png" alt="rating_add"></span>
                                </div>
                            </div>
                        <div class="text">{{ review.text }}</div>
                        <div class="date">{{ review.date }}</div>
                        </div>
                    </div>
                </div>
                <div class="images">
                    <img src="../assets/images/review/review_1.png" alt="review_1">
                    <img src="../assets/images/review/review_2.png" alt="review_2">
                </div>
            </div>
        </div>
    </div>
    </div>
    </template>
    
    <script>
    
    import { ref, computed, onMounted, onUnmounted } from 'vue'
    
    export default {
        name: 'ItemReviews',
        setup() {
    const screenWidth = ref(0);
    const isMobileScreen = computed(() => screenWidth.value >= 360 && screenWidth.value <= 767);

    const handleResize = () => {
      screenWidth.value = window.innerWidth;
    };

    onMounted(() => {
      if (process.client) {
        screenWidth.value = window.innerWidth;
        window.addEventListener('resize', handleResize);
      }
    });

    onUnmounted(() => {
      if (process.client) {
        window.removeEventListener('resize', handleResize);
      }
    });

    return {
      isMobileScreen,
    };
  },
    
        data() {
            return {
                reviews: [
                {
                    avatar: require('../assets/images/review/review_avatar_1.png'),
                    name: 'Алина Мозер',
                    rating: 5,
                    text: 'Отличный комплект! Стоит своих денег, и даже больше! Однозначно рекомендую хрупким девушкам.',
                    date: '26 марта 2023'
                },
                {
                    avatar: require('../assets/images/review/review_avatar_2.png'),
                    name: 'Елена',
                    rating: 5,
                    text: 'Мне нравится этот набор. Ткань такая мягкая, и становится ещё мягче при стирке и носке, не линяет. Цвет я купила гранатовый, он великолепный. С ним чувствую себя комфортно, легко и роскошно одновременно!',
                    date: '2 марта 2023'
                }
            ]
            }
        }
    }
    </script>
    
    <style scoped>
    .wrapper {
        margin: 0 auto;
        width: 1290px;
    }
    .item-reviews {
        margin-top: 70px;
    }
    .reviews-title {
        font-size: 36px;
        text-transform: uppercase;
        font-family: 'maximacyrtcy_lighcomp';
        color: #333934;
    }
    .review-block {
        width: 1200px;
        margin-left: 0;
        display: flex;
        height: 520px;
        justify-content: space-between;
        align-items: flex-end;
        gap: 30px;
    }
    .review {
        width: 740px;
        display: flex;
        gap: 30px;
    }
    .review:first-child {
        height: 183px;
    }
    .review:last-child {
        height: 280px;
    }
    
    .reviews {
        display: flex;
        flex-direction: column;
    }
    .user-info {
        padding-top: 40px;
    }
    .user-name {
        font-family: 'maximacyrtcy_lighcomp';
        color: #333934;
        font-size: 20px;
    }
    .review-content {
        padding-top: 40px;
        display: flex;
        flex-direction: column;
        width: 740px;
    }
    .name-rating {
        display: flex;
        justify-content: space-between;
        padding-bottom: 10px;
    }
    .review-content .text {
        font-family: 'maximacyrtcy_lighcomp';
        color: #333934;
    }
    #text {
        font-size: 14px !important;
    }
    .date {
        padding-top: 10px;
        font-family: 'maximacyrtcy_lighcomp';
        font-size: 16px;
        color: #70756E;
        letter-spacing: 0.025em;
    }
    .images {
        width: 460px;
        display: flex;
        justify-content: space-between;
        gap: 30px;
        padding-bottom: 40px;
    }
    .images > img {
        width: 200px;
        height: 200px;
        object-fit: cover;
    
    }
    @media (min-width: 768px) and (max-width:1366px) {
        .wrapper {
            width: 700px;
            height: 624px;
        }
        .review-block {
            flex-direction: column;
            width: 700px;
            height: 564px;
            margin: 0 auto;
            gap: 0;
        }
    
        .review {
            width: 700px;
        }
        .review:first-child, .review:first-child > div {
            height: 187px;
        }
        .review:last-child, .review:last-child > div {
            height: 167px;
        }
        .images {
            width: 700px;
            justify-content: flex-start;
            padding-bottom: 0;
        }
    }
    @media (min-width:360px) and (max-width:767px) {
        .wrapper {
            margin-top: 40px;
            padding: 0 20px;
            width: 100%;
            min-width:360px;
            max-width: 767px;
            height: 560px;
        }
        .review-block {
            width: 100%;
            min-width:320px;
            max-width: 700px;
            flex-direction: column;
            margin: 0 auto;
        }
        .reviews {
            width: 100%;
        }
        .review {
            max-height: 160px;
            width: 100%;
            max-width: 600px;
        }
        .review-content, .images {
            height: 160px;
            width: 100%;
            max-width: 500px;
        }
        .images {
            margin-top: 30px;
            justify-content: flex-end;
        }
        .images img {
            width: 150px;
            height: 150px;
            object-fit: cover;
        }
        .user-info {
            display: flex;
            flex-direction: column;
            align-items: center;
        }
        .user-name {
            margin-top: 4px;
        }
        .rating {
            display: flex;
            justify-content: space-between;
            align-items: center;
        }
        .date {
            margin-left: 10px;
            margin-bottom: 15px;
        }
    }
    </style>
    