<template>
    <div class="main-container">
      <div class="title">Приятно к телу и планете</div>
      <div class="body-content">
        <div class="box-1">
          <div class="subtitle">Наша компания специализируется на производстве экологически чистого белья</div>
          <div class="description">Мы используем только натуральные и органические материалы, такие как хлопок и лён, в процессе производства, которые безопасны для вашего тела и окружающей среды.</div>
          <div class="body-img">
            <img src="../assets/images/body/body_1.png" alt="body_1">
          </div>
        </div>
        <div class="box-2">
          <div class="body-img">
            <img src="../assets/images/body/body_2.png" alt="body_2">
          </div>
          <button>Узнать больше</button>
        </div>
        <div class="box-3">
          <div class="body-img">
            <img src="../assets/images/body/body_3.png" alt="body_3">
          </div>
          <div class="box-3__content">
          <div class="subtitle">Кроме того, мы стремимся сделать нашу продукцию доступной</div>
          <div class="description">Чтобы каждый мог пользоваться экологически чистым бельём, мы не завышаем стоимость и предлагаем его по разумной цене.</div>
      </div>
      </div>
      </div>
    </div>
</template>

<script>
export default {
  name: 'MainBody'
}
</script>
<style scoped>
.main-container {
  width: 1290px;
  margin: 110px auto 0;
  font-family: 'maximacyrtcy_lighcomp';
  height: 800px;
}
.body-content {
  display: flex;
  justify-content: space-between;
  align-items: center;
  height: 604px;
}
.title {
  text-transform: uppercase;
  font-size: 52px;
  color: #333934;
}
.subtitle {
  font-size: 24px;
  color: #333934;
  text-transform: uppercase;
  padding-bottom: 10px;
}
.description {
  font-size: 18px;
  color: #70756E;
  padding-bottom: 40px;
  letter-spacing: 0.025em;
}
.box-1 {
  width: 520px;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: flex-end;
}

.body-img {
  width: 410px;
}
.box-1 .body-img img {
  width: 410px;
}
.box-2 {
  display: flex;
  flex-direction: column;
  width: 250px;
  position: relative;
}
.box-2 .body-img {
  position: relative;
}
.box-2 .body-img img {
  padding-left: 30px;
  z-index: 1;
}

.box-3 {
  padding-top: 199px;
  width: 520px;
}
.box-3 .body-img {
  width: 520px;
  padding-bottom: 40px;
}
.box-3 .description {
  padding-bottom: 0;
}
button {
  margin: 30px auto 45px;
  width: 100%;
  max-width: 190px;
  height: 60px;
  font-size: 20px; 
  padding: 0 36px;
  background-color: transparent;
  font-family: 'maximacyrtcy_lighcomp';
  text-transform: uppercase;
  color: #333934;
  letter-spacing: 0.025em;
  border: 1px solid #333934;
  cursor: pointer;
  
}

@media screen and (min-width: 768px) and (max-width: 1365px) {
  .main-container {
    min-width: 700px;
    width: 100%;
    max-width: 992px;
    margin: 110px auto 0;
  }
  .body-content {
      flex-wrap: wrap;
      align-items: flex-end;
      min-width: 700px;
    width: 100%;
    max-width: 992px;
  }
  .title {
      margin-left: 30px;
  }
  .box-1 {
      margin-left: 30px;
      width: 60%;

  }
  .box-2 {
      width: 35%;
  }
  .box-2 .body-img {
      width: 220px;

  }
  .box-2 .body-img img {
      width: 220px;
      height: 400px;
      object-fit: cover;
  }
  .box-3 {
      margin-top: 30px;
      padding: 0 35px;
      min-width: 700px;
      max-width: 992px;
      width: 100%;
      display: flex;
      flex-direction: row;
  }
  .box-1 .body-img {
      width: 460px;
  }
  .box-1 .body-img img {
      width: 460px;
      height: 250px;
      object-fit: cover;
      object-position: 60% 0%;

  }
  .box-3 .body-img {
      width: 50%;
  }
  .box-3 .box-3__content {
      width: 50%;
  }
  .box-3 .body-img img {
      width: 340px;
      height: 250px;
      object-fit: cover;
      object-position: 60% 0%;

  }
  button {
      width: 220px;
      margin: 30px 0 0 30px;
  }

}
@media (min-width: 360px) and (max-width: 767px) {
  .main-container {
      margin: 40px auto 0;
      min-width: 320px;
      max-width: 540px;
      width: 100%;

  }
  .main-container > div {
      padding: 20px;
  }
  .body-content {
      min-width: 300px;
      width: 100%;
      display: flex;
      flex-direction: column;
  }
  .title {
      font-size: 30px;
  }
  .subtitle {
      font-size: 20px;
      letter-spacing: 0.025em;
  }
  .description {
      padding-bottom: 0;
  }
  .box-1, .box-2, .box-3 {
      min-width: 300px;
      width: 100%;
  }
  .box-1 {
      order: 1;
  }
  .box-2 {
      order: 3;
  }
  .box-3 {
      order: 2;
  }
  .body-img {
      min-width: 300px;
      width: 100%;
  }
  .box-1 .body-img img {
      display: none;
  }
  .box-3 {
      padding-top: 0;
  }
  .box-3 .body-img {
      width: 320px;
      padding: 20px 0px;
      margin: 0 auto;

  }
  .box-3 .body-img img {
      width: 320px;
      height: 250px;
      object-fit: cover;
  }
  .box-2 .body-img {
      padding: 0px 0px 20px 0;
      
  }
  .box-2 .body-img img {
      width: 320px;
      height: 250px;
      object-fit: cover;
      padding: 20px 0 0;
  }
  img {
      display: block;
      margin: 0 auto;
  }
  button {
      margin: 0px;
      max-width: 540px;
      min-width: 320px;
      height: 60px;
  }
}


</style>
