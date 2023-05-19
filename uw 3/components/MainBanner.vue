<template>
    <div class="banner">
      <div class="container">
        <div class="row">
          <div class="col-12">
            <div class="banner-content">
           <div class="banner-title">
            женское Белье — КАПСУЛЬНАЯ КОЛЛЕКЦИЯ
           </div> 
            <div class="banner-text">комплекты из органического хлопка, безопасного для твоего тела и окружающей среды</div><br/>
            <button class="btn" ><router-link to="/example">перейти в каталог</router-link></button>
            <div class="button-group">
              <div 
                class="btn-small" 
                id="changeBg1"
                :class="{ active: isActive(1) }"
                @click="activate(1)">
              </div>
              <div 
                class="btn-small" 
                id="changeBg2"
                :class="{ active: isActive(2) }"
                @click="activate(2)">
              </div>
              <div 
                class="btn-small" 
                id="changeBg3"
                :class="{ active: isActive(3) }"
                @click="activate(3)">
              </div>
            </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </template>
  
  <script>
  import "../bootstrap-5.0.2/dist/css/bootstrap-grid.min.css";
  
  export default {
  name: "MainBanner",
  data() {
    return {
      activeBtn: 3
    }
  },
  methods: {
    isActive(num) {
      return this.activeBtn === num
    },
    activate(num) {
      this.activeBtn = num
    }
  },
  mounted() {
    const button1 = document.getElementById("changeBg1");
    const button2 = document.getElementById("changeBg2");
    const button3 = document.getElementById("changeBg3");
    const banner = document.querySelector(".banner");

    button1.addEventListener("click", () => {
      banner.classList.remove('banner', 'bg2', 'bg3');
      banner.classList.add('banner', 'bg1');
    });

    button2.addEventListener("click", () => {
      banner.classList.remove('banner', 'bg1', 'bg3');
      banner.classList.add('banner', 'bg2');
    });

    button3.addEventListener("click", () => {
      banner.classList.remove('bg1', 'bg2');
      banner.classList.add('banner');
    });
  },
};
</script>
  
  <style>
  .banner{
    position: relative;
    background-image: url(../assets/images/banner/bg-desktop.png);
    background-size: cover;
    background-position: center;
    background-repeat: no-repeat;
    width: 100%;
    height: 600px; 
  }

  .bg2 {
    background-image: url(../assets/images/body/body_1.png);
  }
  .bg1 {
    background-image: url(../assets/images/body/body_3.png);
  }
  
  @media (max-width: 1366px) {
    .banner {
      background-image: url(../assets/images/banner/bg-laptop.png);
    }
    .bg2 {
    background-image: url(../assets/images/body/body_1.png);
  }
  .bg1 {
    background-image: url(../assets/images/body/body_3.png);
  }
  }
  
  @media (max-width: 768px) {
    .banner {
      background-image: url(../assets/images/banner/bg-tablet.png);
    }
    .bg2 {
    background-image: url(../assets/images/body/body_1.png);
  }
  .bg1 {
    background-image: url(../assets/images/body/body_3.png);
  }
  }
  
  @media (max-width: 360px) {
    .banner {
      background-image: url(../assets/images/banner/bg-mobile.png);
    }
    .bg2 {
    background-image: url(../assets/images/body/body_1.png);
  }
  .bg1 {
    background-image: url(../assets/images/body/body_3.png);
  }
  }
  .banner-content {
    position: absolute;
    top: 100px;
    width: 740px;
    font-family: 'maximacyrtcy_lighcomp';
    text-transform: uppercase;
    color: #fff;
  }
  .banner-title {
    font-size: 100px; 
    font-weight: 400;
    line-height: 110px;
  }
  .banner-text {
    padding-top: 10px;
    font-size: 20px; 
    letter-spacing: 0.025em;
  }
  .banner button {
    width: 350px;
    height: 60px;
    font-size: 20px; 
    margin-top: 18px;
    padding: 10px 20px;
    background-color: transparent;
    font-family: 'maximacyrtcy_lighcomp';
    text-transform: uppercase;
    color: #fff;
    letter-spacing: 0.025em;
    border: 1px solid #fff;
    cursor: pointer;
  }
  @media (max-width: 767px) {
    .banner-content {
        width: 320px;
    }
    .banner-title {
        font-size: 36px;
        line-height: 43px;
    }
    .banner-text {
        line-height: 24px;
    }
    .banner button {
        width: 320px;
    }
  }

  .button-group {
    margin-top: 60px;
    display: flex;
    width: 130px;
    height: 20px;
    justify-content: space-between;
  }
  .button-group:hover {
    cursor: pointer;
  }
  .btn-small {
    width: 40px;
    height: 10px;
    background-color: transparent;
    border-top: 1px solid #fff;
  }
  .btn-small.active {
    border-top: 1px solid grey;

  }
  .btn-small:hover {
    cursor: pointer;
  }
  </style>
  