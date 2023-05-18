<template>
    <div>

    <div v-if="isMobileScreen">
      <header class="header">
  <div class="header-menu"> 
    <div class="header-menu-mob">
      <button class="menu-toggle-btn" @click="isMenuOpen = !isMenuOpen"></button>
    <nav class="navigation" :class="{ show: isMenuOpen }">
    <ul>
      <li><router-link to="/example">Каталог</router-link></li>
      <li><router-link to="/example">Новая коллекция</router-link></li>
      <li><router-link to="/example">Комплекты</router-link></li>
      <li><router-link to="/example">Бюстгальтеры</router-link></li>
      <li><router-link to="/example">трусики</router-link></li>
      <li><router-link to="/example">Купальники</router-link></li>
      <li><router-link to="/example">боди</router-link></li>
    </ul>
  </nav>
    </div>
    <div class="header-menu-mob">
      <img src="../assets/icons/main_logo.png" alt="">
    </div>
    <div class="header-menu-mob">
      <div class="search">   
        <div class="custom-input">
          <img src="../assets/icons/search.png" alt="Search Icon" class="search-icon" />
          <input type="text" class="input-field" v-model="value" @keyup.enter="search" @focus="isFocused = true" @blur="isFocused = false">
        </div>
      </div>
      <div class="cart-alarm" :class="{ 'cart-alarm--active': cartItems.length > 0 }">
            <router-link to="/example"><img src="../assets/icons/cart.png" alt="cart"></router-link>
          </div>
        </div>
      </div>
    </header>
  </div>

  <div v-else>
<header class="header dt">
  <div class="header-menu">      
    <div class="header-menu__item">
      <div class="address-phone">
        <div class="location-container">
          <div class="location-icon"></div>
          <div class="location-city">Санкт-Петербург</div>
        </div>
        <div class="phone-container">
          <div class="plus-icon"></div>
          <div class="number">7 800 800 80 80</div>
        </div>
      </div>
      <div class="search">   
        <div class="custom-input">
          <img src="../assets/icons/search.png" alt="Search Icon" class="search-icon" />
          <input type="text" class="input-field" v-model="value" @keyup.enter="search" @focus="isFocused = true" @blur="isFocused = false">
        </div>
      </div>
    </div>
    <div class="header-menu__item logo">
      <img src="../assets/icons/main_logo.png" alt="">
    </div>
    <div class="header-menu__item">
      <div class="info">
        <router-link to="/example"><div class="info_item">Гарантия</div></router-link>
        <router-link to="/example"><div class="info_item">Доставка</div></router-link>
        <router-link to="/example"><div class="info_item m-none">Контакты</div></router-link>
      </div>
      <div class="icons">
        <div class="icons_item">
          <router-link to="/example"><img src="../assets/icons/profile.png" alt="profile"></router-link>
        </div>
        <div class="icons_item">
          <router-link to="/example"><img src="../assets/icons/heart.png" alt="heart"></router-link>
        </div>     
        <div class="icons_item">
          <div class="cart-alarm" :class="{ 'cart-alarm--active': cartItems.length > 0 }">
            <router-link to="/example"><img src="../assets/icons/cart.png" alt="cart"></router-link>
          </div>
        </div>
      </div>
    </div>
  </div>
  <nav class="navigation">
    <ul>
      <li><router-link to="/example">Каталог</router-link></li>
      <li><router-link to="/example">Новая коллекция</router-link></li>
      <li><router-link to="/example">Комплекты</router-link></li>
      <li><router-link to="/example">Бюстгальтеры</router-link></li>
      <li><router-link to="/example">трусики</router-link></li>
      <li><router-link to="/example">Купальники</router-link></li>
      <li><router-link to="/example">боди</router-link></li>
    </ul>
  </nav>
  <router-view /> 
</header>
</div>
</div>

</template>

<script>
  import { ref, computed, onMounted, onUnmounted } from 'vue'


export default {
  name: 'MainHeader',

  data() {
    return {
      isMenuOpen: false,
      value: '',
      cartItems: [{ id: 1, name: 'Product 1' }],
    }
  },
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


  methods: {
    search() {
      console.log('Searching for:', this.value)
    },
  }
}
</script>

<style scoped>

router-link, a {
    text-decoration: none;
    color: inherit;
}
router-link:visited, a:visited {
    text-decoration: none;
    color: inherit;
}
.header {
  margin: 20px 0 40px;
  height: 163px;
  font-family: 'maximacyrtcy_lighcomp';
  color: #333934;
}
.dt {
    margin-bottom: 30px;
}
.header-menu {
  margin: 0 auto;
  width: 1290px;
  height: 110px;
  display: flex;
  justify-content: center;
}
.header-menu__item {
  width: 33.33%;
}
.header-menu__item:first-child, .header-menu__item:last-child {
  display: flex;
  flex-direction: column;
} 
.header-menu__item > div {
  height: 50%;
}
.address-phone {
  display: flex;
}
.phone {
    display: flex;
}
  .location-container {
    display: flex;
  width: 141px;
}
.location-icon {
  background-image: url(../assets/icons/header_map.png);
  height: 24px;
  width: 24px;
  margin-right: 4px;
}
.location-city {
  font-size: 16px;
  letter-spacing: 0.025em;
}
.phone-container {
  display: flex;
}
.plus-icon {
  background-image: url(../assets/icons/header_plus.png);
  background-position: center center;
  background-repeat: no-repeat;
  background-size: contain;
  margin-right: 4px;
  height: 18px;
  width: 18px;
}
.number {
  font-size: 18px;
  letter-spacing: 0.025em;
}
.custom-input, .custom-mob-input {
  position: relative;
}
.input-field, .input-mob-field {
  border: none;
  background-color: transparent;
  height: 40px;
  padding-left: 30px;
  font-size: 16px;
  outline: none;
}
.search-mob-icon {
  position: absolute;
  left: 5px;
  top: 5px;
  width: 20px;
  height: 20px;
}
.search-icon {
  position: absolute;
  left: 5px;
  top: 5px;
  width: 20px;
  height: 20px;
}
.logo img {
  display: block;
  margin: 0 auto;
  padding-top: 29px;
}
.info, .icons {
  display: flex;
  justify-content: flex-end;
}
.info_item:first-child, .info_item:nth-child(2) {
  margin-right: 30px;
}
.info .m-none {
  margin-right: 0;
}
.icons_item {
  width: 24px;
}
.icons_item:first-child, .icons_item:nth-child(2) {
  margin-right: 20px;
}
.cart-alarm {
  position: relative;
}
.cart-alarm::before {
  content: '';
  display: block;
  position: absolute;
  top: -4px;
  right: -4px;
  width: 12px;
  height: 12px;
  border-radius: 50%;
  background-color: #11442A;
  opacity: 0;
  transition: opacity .2s ease-in-out;
}

.cart-alarm--active::before {
  opacity: 1;
}
.navigation {
  border-top: 1px solid grey;
  padding-top: 15px;
  display: flex;
  justify-content: center;
  font-family: 'maximacyrtcy_lighcomp';
  text-transform: uppercase;
  font-size: 20px;
  letter-spacing: 0.025em;
}

.navigation ul {
    width: 673px;
  list-style-type: none;
  margin: 0;
  padding: 0;
  display: flex;
  justify-content: space-between;
}
.navigation li {
  float: left;
}
.navigation router-link {
  display: block;
  color: #333934;
  text-align: center;
  padding: 14px 16px;
  text-decoration: none;
}
router-link:hover {
  cursor: pointer;
}
.custom-mob-input {
  display: none;
}
@media (max-width: 1366px) {
  .header-menu {
    width: 100%;
    max-width: 1290px;
  }
}
@media (max-width: 768px) {
  .header-menu {
    width: 700px;
    justify-content: space-between;
  }
  nav {
    width: 700px;
    margin: 0 auto;
  }
  .address-phone {
    width: 350px;
  }
  .location-city {
  font-size: 16px;
  letter-spacing: 0.025em;
}
.number {
  min-width: 75px;
}
.logo {
  width: 100px;
}
  .navigation ul li router-link {
    font-size: 20px;
    padding: 14px;
  }
}
.menu-toggle-btn {
  display: none;
}
@media (max-width: 767px) {
  .menu-toggle-btn {
    display: block;
    width: 24px;
    height: 24px;
    background-image: url(../assets/icons/burger.png)
  }
  .navigation {
    position: fixed;
    top: 112px; 
    left: 0;
    width: 100%;
    height: calc(100% - 60px);
    background-color: white;
    z-index: 999;
    transform: translateX(-100%);
    transition: transform 0.3s ease-in-out;
  }
  .navigation ul {
    display: flex;
    flex-direction: column;
  }
  .navigation.show {
    transform: translateX(0);
  }
  .location-container, .phone-container, .info, .icons_item:first-child, .icons_item:nth-child(2) {
    display: none;
  }
  .header {
    height: 54px;
  }
  .header-menu__item {
justify-content: flex-end;
  }
}
@media (min-width: 360px) and (max-width:767px) {
  .header {
    width: 100%;
    min-width: 360px;
    max-width: 767px;
    height: 54px;
  }
  .header-menu {
    margin: 0 auto;
    width: 100%;
    min-width: 320px;
    max-width: 727px;
    height: 94px;
    align-items: center;
  }
.menu-toggle-btn {
  border: none;
  background-color: transparent;
  margin: 0 0 0 20px;
  width: 24px;
  height: 24px;
}
.navigation {
    height: 200px;

  padding-top: 20px;
}
.navigation ul {
    height: 200px;
    justify-content: flex-start;
}
.header-menu-mob:last-child {
display: flex;
padding-right: 20px;
padding-top: 10px;
}
.search {
  width: 30px;
}
.input-field {
  padding: 0;
  width: 30px;
}
.header-menu-mob:nth-child(2) img {
  width: 80px;
  object-fit: cover;
}
}
</style>
