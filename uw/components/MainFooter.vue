<template>
    <div v-if="isMobileScreen">
        <footer>

<div class="footer">

      <div class="footer__mobile">
        <div class="logo"><img src="../assets/images/logo_site.png" alt="logo"></div>
      </div>
      <div class="footer__mobile">
        <div class="footer__item">
          <div class="footer-index">
            <ul class="footer__list">
            <li><router-link to="/example">Каталог</router-link></li>
            <li><router-link to="/example">Новая коллекция</router-link></li>
            <li><router-link to="/example">Комплекты</router-link></li>
            <li><router-link to="/example">Бюстгальтеры</router-link></li>
          </ul>
          </div>
          <div class="footer-index">
            <ul class="footer__list">
              <li><router-link to="/example">Гарантия</router-link></li>
              <li><router-link to="/example">Доставка</router-link></li>
            <li><router-link to="/example">Контакты</router-link></li>
        </ul>
          </div>
        </div>
        <div class="footer__item">
          <div class="footer-index">
            <ul class="footer__list">
          <li><router-link to="/example">Трусики</router-link></li>
          <li><router-link to="/example">Купальники</router-link></li>
          <li><router-link to="/example">Боди</router-link></li>
        </ul>
          </div>
          <div class="footer-index">
            <div class="phone">
          <div class="plus-icon"></div>
          <div class="number">
            7 800 345 10 34
          </div>
        </div>
        <div class="btn"><button>Перезвонить мне</button></div>
          </div>
        </div>
      </div>
      <div class="footer__mobile">
        <div class="footer__item">
            <p>
              © 2023 Impacto Glancie
            </p>
        </div>

          <div class="footer__item">
            <p>
                <router-link to="/example">Пользовательское соглашение</router-link>
            </p>
            <p>
                <router-link to="/example">Политика конфиденциальности</router-link>
            </p>
          </div>
      </div>
      </div>
</footer>

</div>


<div v-else-if="isSmallScreen">
<footer>

<div class="footer">
  <div class="footer__small">
    <div class="logo"><img src="../assets/images/logo_site.png" alt="logo"></div>
    <div class="phone">
          <div class="plus-icon"></div>
          <div class="number">
            7 800 345 10 34
          </div>
        </div>
        <div class="btn"><button>Перезвонить мне</button></div>

  </div>
  <div class="footer__small">
    <div class="footer__item">
          <div class="footer-index">
            <ul class="footer__list">
            <li><router-link to="/example">Каталог</router-link></li>
            <li><router-link to="/example">Новая коллекция</router-link></li>
            <li><router-link to="/example">Комплекты</router-link></li>
            <li><router-link to="/example">Бюстгальтеры</router-link></li>
          </ul>
          </div>
          <div class="footer-index">
            <p>
              © 2023 Impacto Glancie
            </p>
          </div>
        </div>
  </div>
  <div class="footer__small">
    <div class="footer__lasts_els">
      <div class="footer__item">
          <div class="footer-index">
            <ul class="footer__list">
          <li><router-link to="/example">Трусики</router-link></li>
          <li><router-link to="/example">Купальники</router-link></li>
          <li><router-link to="/example">Боди</router-link></li>
        </ul>
          </div>
          <div class="footer-index">
            <p>
                <router-link to="/example">Пользовательское соглашение</router-link>
            </p>
            <p>
                <router-link to="/example">Политика конфиденциальности</router-link>
            </p>
          </div>
        </div>
        <div class="footer__item">
  <div class="footer-index">
          <ul class="footer__list">
            <li><router-link to="/example">Гарантия</router-link></li>
            <li><router-link to="/example">Доставка</router-link></li>
            <li><router-link to="/example">Контакты</router-link></li>
          </ul> 
        </div>
</div>
    </div>

      </div>

  


</div>
</footer>

</div>
<div v-else>
<footer>

  <div class="footer">
      <div class="footer__left">
          <div class="logo"><img src="../assets/images/logo_site.png" alt="logo"></div>
          <div class="copy">
            <p>
              © 2023 Impacto Glancie
            </p> 
          </div>
      </div>
      <div class="footer__center">
        <div class="footer__item">
          <div class="footer-index">
            <ul class="footer__list">
            <li><router-link to="/example">Каталог</router-link></li>
            <li><router-link to="/example">Новая коллекция</router-link></li>
            <li><router-link to="/example">Комплекты</router-link></li>
            <li><router-link to="/example">Бюстгальтеры</router-link></li>
          </ul>
          </div>
          <div class="footer-index">
            <p>
                <router-link to="/example">Пользовательское соглашение</router-link>
            </p>
          </div>
        </div>
        <div class="footer__item">
          <ul class="footer__list">
          <li><router-link to="/example">Трусики</router-link></li>
          <li><router-link to="/example">Купальники</router-link></li>
          <li><router-link to="/example">Боди</router-link></li>
        </ul>
      </div>
      <div class="footer__item">
        <div class="footer-index">
          <ul class="footer__list">
            <li><router-link to="/example">Гарантия</router-link></li>
            <li><router-link to="/example">
                Доставка
            </router-link></li>
            <li><router-link to="/example">
                Контакты
            </router-link></li>
          </ul> 
        </div>
        <div class="footer-index">
          <p>
            <router-link to="/example">Политика конфиденциальности</router-link>
        </p>
        </div>
      </div>
    </div>
      <div class="footer__right">
        <div class="phone">
          <div class="plus-icon"></div>
          <div class="number">
            7 800 345 10 34
          </div>
        </div>
        <div class="btn"><button>Перезвонить мне</button></div>
      </div>
    </div>
</footer>

    </div>


</template>
  
  <script scoped>
  import { ref, computed, onMounted, onUnmounted } from 'vue'

    export default {
    name: 'MainFooter',

    setup() {
    const screenWidth = ref(0);
    const isSmallScreen = computed(() => screenWidth.value >= 768 && screenWidth.value <= 1365)
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
    isSmallScreen,

    };
  },

 

    }

</script>
  <style>
  router-link, a {
    text-decoration: none;
    color: inherit;
}
router-link:visited, a:visited {
    text-decoration: none;
    color: inherit;
}
  router-link:hover {
    cursor: pointer;
  }
  footer {
    width: 100%;
    background-color: #11442A;
    max-height: 372px;
    margin-top: 100px;
    padding: 80px 0;
    color: #fff;
    font-family: 'maximacyrtcy_lighcomp';
    font-size: 18px;
    letter-spacing: 0.025em;
    background-color: #11442A;


  }
  .footer {
    margin: 0 auto;
    width: 1290px;
    display: flex;
    justify-content: space-between;
    align-items:flex-start;
    background-color: #11442A;
  }
  @media (min-width:768px) and (max-width: 1365px) {
   .footer {
    padding: 0 34px;
    min-width: 768px;
    width: 100%;
    max-width: 1290px;
    height: 190px;
   }
   .footer__small:nth-child(2) .footer__item .footer-index:nth-child(1) ul > li,
   .footer__small:nth-child(3) .footer__item .footer-index:nth-child(1) ul > li {
    padding-top: 2px;
   }
   .footer__small:nth-child(3) .footer__item .footer-index:nth-child(2) > p {
    padding-top: 10px;
   }
   .footer__small:nth-child(2) .footer__item .footer-index:nth-child(2) {
    padding-top: 38px;
   }
   .footer__small:nth-child(3) .footer__item .footer-index:nth-child(2) {
    padding-top: 32px;

   }
  }
  .footer__small {
    max-height: 190px;
  }
  .footer__small:first-child {
    padding-left: 34px;
  }
  .footer__small .phone {
    margin-top: 30px;
  }
 .footer__lasts_els {
  display: flex;
  justify-content: start;
 }

.footer__mobile:nth-child(2) {
  margin-top: 30px;
  width: 320px;
  height: 245px;
  display: flex;
  justify-content: space-between;
}
.footer__mobile:nth-child(2) .footer__item:first-child {
  display: flex;
  flex-direction: column;
  justify-content: space-between;
}

.footer__mobile:last-child {
  display: flex;
  flex-direction: row;
  font-size: 16px;
  color: #f9f9f27c;
  width: 320px;
  justify-content: space-between;
  align-items: end;
}
.footer__mobile:last-child .footer__item:last-child p:last-child {
  padding-top: 10px;
}



  .footer__left {
    height: 212px;
    width: 303px;
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    align-items: flex-start;
  }
  .footer__right {
    height: 212px;
    width: 303px;
    display: flex;
    flex-direction: column;
    align-items: flex-end;
  }
  .footer__left {
    width: 400px;
  }

  .footer__center {
    width: 592px;
    height: 212px;

    display: flex;
    justify-content: space-between;


  }
  .footer__center > div {
    width: 33.3%;
  }
  .footer__center .footer__item:first-child {
    padding-left: 3px;
  }
  .footer__center .footer__item:nth-child(2) {
    padding-left: 40px;
  }
  .footer__center .footer__item:last-child {
    padding-left: 48px;
  }
  .footer__center .footer__item {
    display: flex;
    flex-direction: column;
    justify-content: space-between;
  }
  .footer__center .footer__item ul > li {
    padding-top: 2px;
  }
  .footer-index {
  }
  .footer__container--left {
    justify-content: flex-start;
  }
  
  .footer__container--center {
    justify-content: center;
  }
  
  .footer__container--right {
    justify-content: flex-end;
  }
  
  .footer__list {
    list-style: none;
    margin: 0;
    padding: 0;
  }
  
  .footer__list li {
    margin-bottom: 10px;
  }
  .phone {
    display: flex;
    justify-content: end;
    align-items: center;
    text-transform: uppercase;
    font-size: 36px;
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
.footer-index p, .copy p {
  color: #f9f9f27c;
  font-size: 16px;
}
.footer-index p:last-child {
  margin-right: -10px;
}
  button {
    margin-top: 20px;
    width: 190px;
    max-width: 190px;
    height: 50px;
    font-size: 20px; 
    background-color: transparent;
    font-family: 'maximacyrtcy_lighcomp';
    text-transform: uppercase;
    color: #fff;
    letter-spacing: 0.025em;
    border: 1px solid #fff;
    cursor: pointer;
    
  }
  @media (min-width: 360px) and (max-width: 767px) {

footer {
  width: 100%;
  max-width: 767px;
  min-width: 360px;
  min-height: 487px;
margin: 0;
padding: 0;
background-color: #11442A;
}
.footer {
  width: 360px;
  height: 487px;
  margin: 0 auto;
  padding: 50px 60px;
  flex-direction: column;
  justify-content: space-between;
  align-items: center;
background-color: #11442A;

}
button {
  width: 150px;
  height: 50px;
  padding-left: 0;
  padding-right: 0;
}
.number {
  font-size: 28px;
}
} 
  </style>
  