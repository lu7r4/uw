<template>
  <div class="product-cart">
    <div class="path-stars">
      <div class="path">
        <ul>
          <li>Главная</li>
          <li>></li>
          <li>Комплекты</li>
          <li>></li>
          <li>Комплект белья  Red Vine Passion</li>
        </ul>
      </div>
      <div class="stars">
        <span v-for="n in 6" :key="n" class="star">
  <img src="../assets/icons/rating_add.png" alt="rating_add">
</span>
      </div>
    </div>
    <div class="description">

      <div class="about-product">

        <div class="title">
          Комплект белья  Red Vine Passion New collection 
        </div>
        <div class="price">
          12 800 ₽ 
        </div>

        <div class="main-description">
          <p>Это соблазнительное изделие из винного декоративного кружева. 
          </br>Великолепный кружевной бюстгальтер без подкладки, с ремешками и вырезами,этот бюстгальтер будет хорошо смотреться на вас со всех сторон. </p>
          Кружевные чашечки без подкладки.
          <p>

          Трусики выполнены в том же стиле. Мягкие стринги по бокам позволяют незаметно носить этитрусики под одеждой.</p>
        </div>
<div class="color-size">
<div class="main-color">

        <div class="color-title">цвет</div>

  <div class="flex-container">
    <div class="color-wrapper">
      <div
        class="color-option"
        :class="{ selected: selectedColor === 'red' }"
        @click="selectedColor = 'red'"
      ></div>
      <div
        class="color-option"
        :class="{ selected: selectedColor === 'green' }"
        @click="selectedColor = 'green'"
      ></div>
      <div
        class="color-option"
        :class="{ selected: selectedColor === 'blue' }"
        @click="selectedColor = 'blue'"
      ></div>
    </div>
</div>
</div>

<div class="main-size">

    <div class="size-title">Размер</div>
    <div class="size-wrapper">
      <div
        class="size-option"
        :class="{ selected: selectedSize === 's' }"
        @click="selectedSize = 's'"
      >S</div>
      <div
        class="size-option"
        :class="{ selected: selectedSize === 'm' }"
        @click="selectedSize = 'm'"
      >M</div>
      <div
        class="size-option"
        :class="{ selected: selectedSize === 'l' }"
        @click="selectedSize = 'l'"
      >L</div>
      <div
        class="size-option"
        :class="{ selected: selectedSize === 'xl' }"
        @click="selectedSize = 'xl'"
      >XL</div>
    </div>
</div>



</div>

    
    <div class="button-wrapper">
      <button class="order-button">Заказать</button>
      <div class="heart" 
    :class="{ 'active': isFavorite }">
    <input type="checkbox" class="checkbox" v-model="isFavorite" @change="toggleFavorite()">
</div>
    </div>
</div>

    <div class="container-images">
      <div class="small-images">
        <img v-for="(image, index) in smallImages" :key="index" :src="image.src" :class="{ activeimg: activeIndex === index }" @click="showBigImage(index)">
      </div>
      <div class="big-image">
        <img v-if="bigImage" :src="bigImage.src">
      </div>
    </div>

  </div>


  </div>

  </template>
  
  <script>
  export default {
    name: 'ItemProductCard',
    data() {
      return {
        smallImages: [
          { src: require('../assets/images/product_cart/sm1.png') },
          { src: require('../assets/images/product_cart/sm2.png') },
          { src: require('../assets/images/product_cart/sm3.png') }
        ],
        bigImage: null,
        activeIndex: 2,

        selectedColor: 'red',
        selectedSize: 'l',
        isFavorite: false


      }
    },
    methods: {
      toggleFavorite() {
  this.isFavorite = !this.isFavorite;
},

      showBigImage(index) {
        this.bigImage = this.smallImages[index];
        this.activeIndex = index;
      }
    },
    mounted() {
      this.bigImage = this.smallImages[this.activeIndex];
    }
  }
  </script>
  
  <style scoped>
  .product-cart {
    margin: 0 auto;
    display: flex;
    flex-direction: column;
    width: 1290px;
    height: 725px;
  }
  .path-stars {
    display: flex;
    justify-content: space-between;
    height: 24px;
    width: 100%;
  }
  .path ul {
    font-family: 'maximacyrtcy_lighcomp';
    display: flex;
    width: 300px;
  }
  ul, li {
    font-size: 16px;
    letter-spacing: 0.025em;
    font-family: 'maximacyrtcy_lighcomp';
  margin: 0 2px;
  padding: 0;
  list-style: none;
  color: #333934;
}
li:last-child {
  color: #DAD7CD;
}

.stars {
  width: 120px;
  height: 24px;
}
.description {
  display: flex;
  justify-content: space-between;
  width: 1290px;
  height: 700px;
}
.about-product {
  display: flex;
  flex-direction: column;
  width: 550px;
  height: 700px;
}
.title {
  font-family: 'maximacyrtcy_lighcomp';
  text-transform: uppercase;
  color: #333934;
  font-size: 52px;
  width: 520px;
  height: 124px;
  line-height: 140%;
}
.price {
  font-family: 'maximacyrtcy_lighcomp';
  text-transform: uppercase;
  color: #333934;
  font-size: 40px;
  margin: 10px 0 20px;
}
.main-description {
  width: 520px;
  height: 160px;
  color: #333934;
  line-height: 140%;
  font-family: 'maximacyrtcy_lighcomp';

}
.main-description > p {
  margin-bottom: 5px;

}
  .container-images {
    max-width: 810px;

    margin-top: 0;
    display: flex;
    justify-content: space-between;
  }
  
  .small-images {
    height: 270px;
    width: 70px;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: space-between;
  }
  
  .small-images img {
    width: 70px;
    height: 70px;
    margin-left: 0;
    cursor: pointer;
    opacity: 1;
  }
  
  .small-images img.activeimg {
    opacity: 0.5;
    border: none;
  }
  
  .big-image {
    margin-left: 20px;
  }
  
  .big-image img {
    width: 630px;
    height: 700px;
  }


  .flex-container {
  display: flex;
  flex-direction: column;
}

.color-wrapper {
  display: flex;
}

.color-option {
  position: relative;
  width: 24px;
  height: 24px;
  margin-right: 10px;
  cursor: pointer;
}
.color-option:first-child.selected,
.color-option:first-child {
  background-color: #6C252B;
}
.color-option:nth-child(2),
.color-option:nth-child(2).selected {
  background-color: #1C6031;
}
.color-option:last-child,
.color-option:last-child.selected {
  background-color: #70B2E2;
}
.color-option.selected::before {
  position: absolute;
  content: "";
  top: 2px;
  left: 2px;
  width: 16px;
  height: 16px;
  background-color: transparent;
}
.color-option.selected::after {
  position: absolute;
  content: "";
  top: 2px;
  left: 2px;
  width: 16px;
  height: 16px;
  border: 2px solid #fff;
  background-color: transparent;
}
.size-title, .color-title {
  font-family: 'maximacyrtcy_lighcomp';
  color:#333934;
  font-size: 20px;
  letter-spacing: 0.025em;
  text-transform: uppercase;
  margin-bottom: 10px;
}
.size-title {
  margin-top: 30px;
}
.size-wrapper {
  display: flex;
  justify-content: space-between;
  width: 270px;
}

.size-option {
  width: 60px;
  height: 36px;
  display: flex;
  align-items: center;
  justify-content: center;
  background-color: transparent;
  color: #11442A;
  border: 1px solid #DAD7CD;
  font-family: 'maximacyrtcy_lighcomp';

}

.size-option.selected {
  background-color: #11442A;
  color: white;
}

.button-wrapper {
  display: flex;
  width: 520px !important;
  align-items: flex-end;
}

.order-button {
  width: 450px !important;
  max-width: 450px;
  height: 60px;
  background-color: #11442A;
  color: white;
  letter-spacing: 0.025em;
  font-size: 20px;
  font-family: 'maximacyrtcy_lighcomp';
  border: none;
  margin-top: 40px;
}


.heart, .active {
  margin-left: 20px;
  padding: 5px;
    width: 60px;
    height: 60px;
    background-image: url(../assets/icons/heart.png);
    background-position: center center;
    background-size: auto;
    background-repeat: no-repeat;
    border: 1px solid #11442A;
  }
  .active {
    width: 60px;
    height: 60px;
    background-image: url(../assets/icons/heart_active.png);
    background-position: center center;
    background-size:auto;
    background-repeat: no-repeat;

  }
  input {
    opacity: 0;
  }
  @media (min-width: 768px) and (max-width: 1365px) {
    .product-cart {
      width: 728px;
      height: 1050px;
    }
    .path-stars {
      width: 620px;
      width: 100%;
    }
    .path {
      padding-left: 20px;
    }
    .stars {
      display: none;
    }
    .description {
      flex-direction: column;
      width: 620px;
    }
    .about-product {
      order: 2;
      width: 620px;
      padding-left: 20px;
    }
    .container-images {
      order: 1;
      width: 620px;
      gap: 20px;
    }
    .small-images {
      order: 2;
    }
    .big-image {
      order: 1;
    }
    .big-image img {
      object-fit: cover;
      width: 580px;
      height: 500px;
    }
    .color-size {
      display: flex;
      justify-content: space-between;
      align-items: flex-start;
      height: 70px;
      width: 520px;
    }
    .main-size {
      width: 270px;
      order: 1;
      height: 70px;
    }
    .main-color {
      order: 2;
      width: 190px;
      height: 58px;
    }
    .size-title {
      margin: 0 0 10px;
    }
  }
  @media (min-width: 360px) and (max-width: 767px) {
    .product-cart {
      margin-top: 80px;
      width: 320px;
      height: 900px;
      flex-direction: column;
    }
    .description {
      flex-direction: column;
      width: 320px;
    }
    .container-images {
      order: 1;
      width: 320px;
    }
    .stars {
      display: none;
    }
    .path {
      max-width: 320px;
      margin-left: 20px;
      font-size: 16px;
    }
    .about-product {
      width: 320px;
      order: 2;
    }
    .title, .price {
      font-size: 36px;
      width: 320px;
      margin-left: 20px;
    }
    .price {
      margin-bottom: 0;
    }
    .main-description {
      width: 320px;
      height: 110px;
      font-size: 14px;
      margin-left: 20px;
    }
    .color-size {
      display: flex;
      flex-direction: column;
      width: 320px;
      align-items: flex-start;
      margin-left: 20px;

    }
    .button-wrapper {
      max-width: 320px;
      margin-left: 20px;
    }
    .order-button {
      max-width: 250px;
    }
    .main-size {
      width: 320px;
      order: 1;
    }
    .main-color {
      width: 320px;
      order: 2;
    }
    .images {
      width: 320px;
    }
    .small-images {
      display: none;
    }
    .big-image img {
      width: 320px;
      height: 320px;
    }
  }

  </style>
  