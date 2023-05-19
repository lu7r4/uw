<template>
    <div class="wrapper">
      <div class="main-container">
        <div class="main-title">Вы также смотрели</div>
        <div class="product-list">
          <div v-for="(product, index) in productData" :key="index" class="product-card">
            <div class="image">
                <img :src="product.image" :alt="product.name" />

                <div v-if="hasHotLabel(product)" class="hot-label">{{ product.hotLabeL }}</div>
                <div v-if="hasSaleLabel(product)" class="sale-label">{{ product.saleLabeL }}</div>

                <div class="heart" 
                    :class="{ 'active': product.isFavorite }">
                    <input type="checkbox" class="checkbox" v-model="product.isFavorite" @change="toggleFavorite(product)">
            
                </div>


            </div>
            <div class="name">{{ product.name }}</div>
            <div class="price-add">
                <div class="price-flex">

                    <div v-if="hasOldPrice(product)" class="old-price">{{ product.oldPrice }}</div>
                    
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
    name: 'ItemCards',
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
            name: 'Бюстгальтер Треугольной Формы In Full Bloom',
            image: require('../assets/images/cart_item/cart_item_1.png'),
            price: 3650,
            hotLabeL: 'HOT!',
            isFavorite: false
          },
          {
            id: 2,
            name: 'комплект black edition',
            image: require('../assets/images/cart_item/cart_item_2.png'),
            price: 7900,
            isFavorite: true
          },
          {
            id: 3,
            name: 'комплект blue flossom',
            image: require('../assets/images/cart_item/cart_item_3.png'),
            oldPrice: 9000,
            price: 8700,
            saleLabeL: 'SALE!',
            isFavorite: false
          },
          {
            id: 4,
            name: 'комплект Cotton',
            image: require('../assets/images/cart_item/cart_item_4.png'),
            price: 5400,
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
      hasOldPrice(product) {
        return product.oldPrice !== undefined;
      },
      hasHotLabel(product) {
        return product.hotLabeL !== undefined;
      },
      hasSaleLabel(product) {
        return product.saleLabeL !== undefined;
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
  .main-title {
    margin-bottom: 50px;
    text-transform: uppercase;
    font-size: 36px;
    color: #333934;
    font-family: 'maximacyrtcy_lighcomp';
  }
  .product-list {
    display: flex;
    justify-content: space-between;
    align-items: center;
  }
  .product-card {
    width: 290px;
    height: 430px;
  }
  .product-card img {
    width: 290px;
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
  .product-card .old-price {
    text-decoration: line-through;
    color: #70756E;
    font-size: 20px;
    text-transform: uppercase;
  }
  
  .product-card .price {
    font-family: 'maximacyrtcy_lighcomp';
text-transform: uppercase;
   color: #11442A;
   font-size: 24px;
  }
  
  .product-card .add-to-cart-button {
    display: block;
    margin-top: 10px;
    padding: 10px;
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
  .hot-label, .sale-label {
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
  .sale-label {
    background-color: #70756E;
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
        max-width: 1366px;
        width: 100%;
    }
    .product-list {
        margin: 0 auto;
        min-width: 700px;
        max-width: 1290px;
        width: 100%;
    }
    .product-card .product-card > div, .image {
        width: 220px;
    }
    .name {
        width: 220px;
    }
    .product-card img {
        width: 220px;
    }
    .product-card:last-child {
        display: none;
    }
  }
  @media (min-width: 360px ) and (max-width: 767px) {
    .main-container {
        min-width: 320px;
        width: 100%;
    }
    .product-list {
        margin: 0 auto;
        min-width: 320px;
    }
    .product-card .image {
        max-width: 150px;
    }
    .name {
        width: 150px;
    }
    .product-card img {
        width: 150px;
        height: 270px;
    }
    .product-card:nth-child(3),
    .product-card:last-child {
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
  }
  

  </style>