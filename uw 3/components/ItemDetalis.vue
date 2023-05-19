<template>
    <div class="container">

      <div class="detalis">
        <div class="characteristics">
          <div class="characteristics-title">Подробности</div>
          <div class="characteristics-descriotion">

          <div class="keys">
        <div
          class="key"
          :class="{ active: activeIndex === 0 }"
          @click="activeIndex = 0"
        >
          Характеристика
          <div
                class="vertical-line"
                :class="{ active: activeIndex === 0 }"
              ></div>
        </div>
        <div
          class="key"
          :class="{ active: activeIndex === 1 }"
          @click="activeIndex = 1"
        >
          Состав
          <div
                class="vertical-line"
                :class="{ active: activeIndex === 1 }"
              ></div>
        </div>
        <div
          class="key"
          :class="{ active: activeIndex === 2 }"
          @click="activeIndex = 2"
        >
          Уход
          <div
                class="vertical-line"
                :class="{ active: activeIndex === 2 }"
              ></div>
        </div>
      </div>


      <div class="values">
        <div v-if="activeIndex === 0"><span>Lorem</span> ipsum dolor sit, amet consectetur adipisicing elit. Ratione dolore eum, expedita labore doloribus voluptates nostrum rerum, dignissimos quaerat, fugit tempore ea! Voluptatum dolorem esse accusantium aliquam dolore, illo natus.</div>
        <div v-if="activeIndex === 1"><p> <span> Модал </span>  — ткань, получаемая из эвкалиптового волокна. Обладает шелковистым блеском, мягкостью и высокой прочностью. Позволяет регулировать температуру тела. </p>
        <p><span>Хлопок</span> — натуральный, мягкий, комфортный в носке. Ткань отличается высокой способностью к впитыванию влаги, комфортна и в жаркую, и в холодную погоду.</p></div>
        <div v-if="activeIndex === 2"><span>Lorem</span>, ipsum dolor sit amet consectetur adipisicing elit. Aspernatur rem fuga et impedit temporibus quia. Placeat corporis quod error non soluta quis tempore, libero pariatur ipsa magni excepturi iure alias.</div>
      </div>
    </div>

  

        </div>
    <div class="fashion">
      <div class="fashion-title">Дополнить образ</div>
      <div class="fashion-images">
        <img src="../assets/images/detalis/detalis_1.png" alt="detalis_1">
        <img src="../assets/images/detalis/detalis_2.png" alt="detalis_2">
      </div>
    </div>
  </div>
      
    </div>
  </template>
  
  <script>
  export default {
    name: 'ItemDetalis',
    data() {
      return {
        activeIndex: 1,
      };
    },
  };
  </script>
  
  <style>
  .container {
    margin-top: 50px;

    width: 100%;
    min-width: 1366px;
    max-width: 1920px;
  }
  .detalis {
    display: flex;
    justify-content: space-between;
    margin: 0 auto;
    width: 1290px;
  }
  .characteristics-title, .fashion-title {
    margin-bottom: 30px;
    font-family: 'maximacyrtcy_lighcomp';
    font-size: 36px;
    text-transform: uppercase;
  }
  .characteristics {
    display: flex;
    flex-direction: column;
    width: 628px;
  
  }
  .characteristics-descriotion {
    display: flex;
    justify-content: space-between;
    height: 147px;
  }
  
  .keys {
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    width: 147px;
    position: relative;
    
  }
  .keys::after {
    position: absolute;
    content: '';
    height: 100%;
    width: 1px;
    top: 0;
    right: 1px;
    background-color: #DAD7CD;
  }
  
  .key {
    margin: 10px 0 16px;
    cursor: pointer;
    font-family: 'maximacyrtcy_lighcomp';
    font-size: 20px;
    letter-spacing: 0.025em;
    color: #70756E;
    position: relative;
  }
  
  .key.active {
    color: black;
  }
  
  .values {
    width: 541px;
    padding: 10px 25px 0;
    font-family: 'maximacyrtcy_lighcomp';
    letter-spacing: 0.07em;
    color: #333934;
  }
  .values p span {
    color: #000;
 
  }
  .values p:first-child {
    margin-bottom: 10px;
  }
  .fashion {
    width: 410px;
  }
  .fashion-images {
    display: flex;
    justify-content: start;
    align-items: flex-start;
    gap: 30px;
  }
  .vertical-line {
  position: absolute;
  top: 0;
  right: 0;
  height: 100%;
  width: 1px;
  background-color: transparent;
  transform: scale(0);
  
}

.key.active .vertical-line {
  transform: scale(1);
  background-color: black;
  width: 2px;
}

@media (min-width:768px) and (max-width:1366px) {
  .container {
    width: 100%;
    min-width: 768px;
    max-width: 1366px;

  }
  .detalis {
    flex-direction: column;
    width: 700px;
    margin: 0 auto;
  }
  .fashion {
    margin-top: 70px;
  }
}
@media (min-width:360px) and (max-width:767px) {
  .container {
    width: 100%;
    min-width: 360px;
    max-width: 767px;

  }
  .detalis {
    flex-direction: column;
    width: 320px;
    margin: 0 auto;
  }
  .fashion {
    margin-top: 70px;
  }
  .characteristics {
    width: 320px;
  }
  .characteristics-descriotion {
    flex-direction: column;
    width: 320px;
  }
  .values {
    padding-left: 0;
    width: 320px;
  }
  .keys {
    flex-direction: row;
    gap: 20px;
    width: 320px;
  }
  .keys::before {
    position: absolute;
    content: '';
    height: 1px;
    width: 100% !important;
    bottom: 0;
    left: 0;
    background-color: #DAD7CD;
  }
  .keys::after {
    display: none;
  }
  .key.active .vertical-line {
  transform: scale(1);
  background-color: black;
  height: 2px;
  width: 100%;
}
  .vertical-line {
  position: absolute;
  top: 39px;
  left: 0;
  height: 1px;
  width: 100% ;
  background-color: transparent;
  transform: scale(0);
  
}
}
  </style>
  