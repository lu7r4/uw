<template>
    <div class="wrapper">
      <div class="main-container">
        <div class="title-btn">
            <div class="main-title">новые поступления</div>
            <button class="btn">Смотреть все</button>
        </div>
        <div class="product-list">
          <div v-for="(product, index) in productData" :key="index" class="product-card">
            <div class="image">
                <img :src="product.image" :alt="product.name" />

                <div v-if="hasHotLabel(product)" class="hot-label">{{ product.hotLabeL }}</div>


                <div class="heart" 
                    :class="{ 'active': product.isFavorite }">
                    <input type="checkbox" class="checkbox" v-model="product.isFavorite" @change="toggleFavorite(product)">
            
                </div>


            </div>
            <div class="name">{{ product.name }}</div>
            <div class="price-add">
                <div class="price-flex">


                    
                    <div class="price">{{ product.price }} P</div>

                </div>
                    <button @click="addToCart(product.id)" class="add-to-cart-button">
                    <img src="../assets/icons/cart.png" alt="cart">
                    </button>
            </div>

          </div>
        </div>
      </div>
    </div> 
  </template>
  
  <script>
  export default {
    name: 'MainCards',
    props: {
    itemId: {
      type: Number,
      required: true,
    },
  },
    data() {
      return {
        productData: [
          {
            id: 1,
            name: 'Комплект для невесты In Full Bloom ',
            image: require('../assets/images/goods/goods_1.png'),
            price: 13650,
            hotLabeL: 'HOT!',
            isFavorite: false
          },
          {
            id: 2,
            name: 'комплект red flossom',
            image: require('../assets/images/goods/goods_2.png'),
            price: 8700,
            isFavorite: false
          },
          {
            id: 3,
            name: 'комплект Gorgeous and Strict',
            image: require('../assets/images/goods/goods_3.png'),
            price: 8700,
            isFavorite: false
          },
          {
            id: 4,
            name: 'Комплект для невесты In Full Bloom',
            image: require('../assets/images/goods/goods_4.png'),
            price: 13650,
            isFavorite: true
          },
          {
            id: 5,
            name: 'трусики pink lady edition',
            image: require('../assets/images/goods/goods_5.png'),
            price: 1900,
            hotLabeL: 'HOT!',
            isFavorite: false
          },
          {
            id: 6,
            name: 'комплект sunny Cotton',
            image: require('../assets/images/goods/goods_6.png'),
            price: 15400,
            hotLabeL: 'HOT!',
            isFavorite: true
          },
        ],
      };
    },
    methods: {
        toggleFavorite(product) {
            this.$set(product, 'isFavorite', !product.isFavorite);
    },
      addToCart(productId) {
        console.log(`Добавлен товар с ID ${productId} в корзину`);
      },

      hasHotLabel(product) {
        return product.hotLabeL !== undefined;
      }
    },
  };
  </script>
  
  <style scoped>
  .wrapper {
    margin-top: 50px;
    width: 100%;
  }
  .main-container {
    width: 1290px;
    margin: 0 auto;
  }
  .title-btn {
    display: flex;
    justify-content: space-between;
    align-items: center;
  }
  .btn {
    text-transform: none;
    background-color: transparent;
    font-family: 'maximacyrtcy_lighcomp';
    color: #70756E;
    font-size: 18px;
    letter-spacing: 0.025em;
    margin-top: 0;
  }
  .main-title {
    padding-left: 30px;
    text-transform: uppercase;
    font-size: 36px;
    color: #333934;
    font-family: 'maximacyrtcy_lighcomp';
  }
  .product-list {
    display: flex;
    justify-content: space-between;
    align-items: center;
    flex-wrap: wrap;
    margin-top: 50px;
  }
  .product-card {
    width: 290px;
    height: 430px;
    margin-bottom: 30px;
  }
  .product-card:first-child, .product-card:last-child {
    width: 620px;
    height: 430px;
  }
  .product-card img {
    width: 290px;
    height: 350px;
    object-fit: cover;
  }
  .product-card:first-child img, .product-card:last-child img {
    width: 620px;
    height: 350px;
    object-fit: cover;
  }
  
  .product-card img {
    max-width: 100%;
    height: auto;
  }
  
  .product-card .name {
    font-family: 'maximacyrtcy_lighcomp';
    letter-spacing: 0.025em;
    text-transform: uppercase;
    font-size: 20px;
    margin-top: 10px;
  }
  .price-add {
    display: flex;
    justify-content: space-between;
    align-items: center;
  }
  .price-flex {
    display: flex;
    align-items: center;
    gap: 10px;
  }

  
  .product-card .price {
    font-family: 'maximacyrtcy_lighcomp';
    text-transform: uppercase;
   color: #11442A;
   font-size: 24px;
  }
  
  .product-card .add-to-cart-button {
    width: 34px;
    display: block;
    padding: 0;
    margin-top: 10px;
    background-color: transparent;
    border: none;
    cursor: pointer;
  }
  
  .product-card .add-to-cart-button img {
    max-width: 20px;
    height: auto;
  }
  .image {
    position: relative;
  }
  .hot-label {
    font-family: 'maximacyrtcy_lighcomp';
    padding-top: 6px;
    text-align: center;
    text-transform: uppercase;
    position: absolute;
    width: 70px;
    height: 31px;
    background-color: #11442A;
    color: #fff;
    left: 20px;
    top: 20px;
  }

  .heart, .active {
    position: absolute;
    top: 20px;
    right: 20px;
    width: 24px;
    height: 24px;
    background-image: url(../assets/icons/heart.png);
    background-position: center center;
    background-size: cover;
    background-repeat: no-repeat;
  }
  .active {
    position: absolute;
    top: 20px;
    right: 20px;
    width: 24px;
    height: 24px;
    background-image: url(../assets/icons/heart_active.png);
    background-position: center center;
    background-size: cover;
    background-repeat: no-repeat;
  }
  input {
    opacity: 0;
  }

  @media (min-width: 768px) and (max-width: 1366px) {
    .main-container {
        min-width: 768px;
        max-width: 880px;
        width: 100%;
    }
    .product-list {
        padding: 0 20px;
        margin: 0 auto;
        min-width: 700px;
        max-width: 870px;
        width: 100%;
    }
    .product-card {
    width: 220px;
    height: 430px;
    margin-bottom: 40px;
  }
  .product-card:first-child, .product-card:last-child {
    width: 220px;
    height: 430px;
  }
  .product-card img {
    width: 220px;
    height: 350px;
    object-fit: cover;
  }
  .product-card:first-child img, .product-card:last-child img {
    width: 220px;
    height: 350px;
    object-fit: cover;
  }
  
.add-to-cart-button {
    width: 34px;
    height: 34px;
    padding-left: 0;
}
.add-to-cart-button img {
    width: 20px;
    max-height: 20px;
}
.name {
    font-size: 20px;
}
.price {
    font-size: 20px;

}
  }
  @media (min-width: 360px ) and (max-width: 767px) {
    .main-container {
        min-width: 320px;
        width: 100%;
    }
    .main-title {
        max-width: 360px;
        margin: 0 auto;
        padding-left: 0;
        padding-bottom: 50px;
    }
    .product-list {
        margin: 20px auto 0;
        min-width: 320px;
        max-width: 400px;
        height: 420px;
        padding: 0 20px;
    }
 
    .name {
        width: 150px;
    }
    .product-card:first-child, .product-card:nth-child(2) {
        width: 100%;
        max-width: 150px;
    }
    .image {
        width: 150px;
    }
    .product-card:first-child .image img, .product-card:nth-child(2) .image  img{
        max-width: 150px;
        width: 100%;
        height: 270px;
        object-fit: cover;
    }

    .add-to-cart-button img {
        width: 34px;
        height: 34px;
    }
    .product-list > :nth-child(n+3) {
        display: none;
    }
    .name {
        font-size: 16px;
    }
    .price {
        font-size: 18px;
    }
    .price-flex {
      flex-direction: column;
    }
    .title-btn {
        margin: 0 auto;
        max-width: 360px;
    }
    .main-title {
        margin: 0;
        font-size: 30px;
        padding-bottom: 0;
    }
    .btn {
        font-size: 16px;
        width: 70px;
    }
  }
  

  </style>