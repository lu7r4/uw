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


  <div class="flex-container">
    <!-- Компоненты выбора цвета -->
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
    
    <!-- Компоненты выбора размера -->
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
    
    <!-- Компоненты заказа и кастомного чекбокса -->
    <div class="button-wrapper">
      <button class="order-button">Заказать</button>
      <div class="heart" 
    :class="{ 'active': isFavorite }">
    <input type="checkbox" class="checkbox" v-model="isFavorite" @change="toggleFavorite()">
</div>
    </div>
  </div>
</div>



    <div class="container-images">
      <div class="small-images">
        <img v-for="(image, index) in smallImages" :key="index" :src="image.src" :class="{ active: activeIndex === index }" @click="showBigImage(index)">
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
          { src: 'https://via.placeholder.com/80x80' },
          { src: 'https://via.placeholder.com/80x80' },
          { src: 'https://via.placeholder.com/80x80' }
        ],
        bigImage: null,
        activeIndex: 2,

        selectedColor: null,
        selectedSize: null,
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
    border: 1px solid #000;
    display: flex;
    flex-direction: column;
    width: 1290px;
    height: 725px;
  }
  .path-stars {
    display: flex;
    justify-content: space-between;
    border: 1px solid blue;
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
  border: 1px solid red;
}
.about-product {
  display: flex;
  flex-direction: column;
  width: 550px;
  height: 700px;
  border: 1px solid #000;
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
  border: 1px solid red;
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
    margin-bottom: 10px;
    cursor: pointer;
    opacity: 1;
  }
  
  .small-images img.active {
    opacity: 0.5;
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

.color-option {
  width: 24px;
  height: 24px;
}

.color-option.selected {
  border: 2px solid white;
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

  </style>
  