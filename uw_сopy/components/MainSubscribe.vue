<template>

    <div v-if="isSmallScreen">
    <div class="main-small">
      <div class="subscribe-content">
    
                          <div class="subscribe-form">
                              <div class="form">
                                  <div class="form-title">стань первым, кто узнает</div>
                                  <div class="form-description">Присоединяйся к нам, чтобы быть в курсе последних обновлений и
                                      получать специальные скидки и предложения.</div>
                                  <form @submit.prevent="submitForm">
                                      <div class="form-row">
    
                                          <div class="custom-input">
                                              <input type="email" id="email" v-model.trim="email" required
                                                  placeholder="Введите адрес электронной почты">
                                          </div>
    
    
                                          <button :disabled="!isValid" class="btn">Подписаться</button>
    
                                      </div>
                                      <div class="main-checkbox">
    
                                          <div class="checkbox-container" @click="toggleCheckbox">
                                              <div :class="['checkbox', { 'checked': isChecked }]" id="agree">
                                                  <svg v-if="isChecked" xmlns="http://www.w3.org/2000/svg" width="20"
                                                      height="20" viewBox="0 0 24 24">
                                                      <path fill="#FFF"
                                                          d="M9 16.2L4.8 12l-1.4 1.4 5.6 5.6L22.6 6.4l-1.4-1.4z" />
                                                  </svg>
                                              </div>
                                          </div>
                                          <label for="agree" class="agree-label">Даю согласие на обработку персональных
                                              данных</label>
                                      </div>
    
    
    
                                  </form>
                              </div>
                          </div>
                          <div class="subscribe-img">
                              <img src="../assets/images/subscription/subscription.png" alt="subscribe">
                          </div>
                      </div>
    </div>
</div>    
    <div v-else>

      <div class="main-subscribe">
          <div class="container">
              <div class="row">
                  <div class="col-12">
                      <div class="bg-color"></div>
                      <div class="subscribe-content">
                          <div class="subscribe-img">
                              <img src="../assets/images/subscription/subscription.png" alt="subscribe">
                          </div>
                          <div class="subscribe-form">
                              <div class="form">
                                  <div class="form-title">стань первым, кто узнает</div>
                                  <div class="form-description">Присоединяйся к нам, чтобы быть в курсе последних обновлений и
                                      получать специальные скидки и предложения.</div>
                                  <form @submit.prevent="submitForm">
                                      <div class="form-row">
    
                                          <div class="custom-input">
                                              <input type="email" id="email" v-model.trim="email" required
                                                  placeholder="Введите адрес электронной почты">
                                          </div>
                                          <button :disabled="!isValid">Подписаться</button>
    
                                      </div>
                                      <div class="main-checkbox">
    
                                          <div class="checkbox-container" @click="toggleCheckbox">
                                              <div :class="['checkbox', { 'checked': isChecked }]" id="agree">
                                                  <svg v-if="isChecked" xmlns="http://www.w3.org/2000/svg" width="20"
                                                      height="20" viewBox="0 0 24 24">
                                                      <path fill="#FFF"
                                                          d="M9 16.2L4.8 12l-1.4 1.4 5.6 5.6L22.6 6.4l-1.4-1.4z" />
                                                  </svg>
                                              </div>
                                          </div>
                                          <label for="agree" class="agree-label">Даю согласие на обработку персональных
                                              данных</label>
                                      </div>
    
    
    
                                  </form>
                              </div>
                          </div>
                      </div>
                  </div>
              </div>
          </div>
      </div>
    </div>
    
    </template>
      
      <script>
      import { ref, computed, onMounted, onUnmounted } from 'vue'
    
      export default {
        name: 'MainSubscribe',
    
        setup() {
          const screenWidth = ref(0);
          const isSmallScreen = computed(() => screenWidth.value >= 360 && screenWidth.value <= 1365)

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
            isSmallScreen,

            };
          },
    
        data() {
          return {
            email: '',
            isChecked: false,
            subscribeContent: ''
          }
        },
    
        computed: {
          isValid() {
            return this.email && this.agreed
          }
        },
        methods: {
            toggleCheckbox() {
          this.isChecked = !this.isChecked;
            }, 
          async submitForm() {
            if (!this.isValid) return;
    
            const data = {
              email: this.email,
              agreed: this.agreed
            };
    
            try {
              await fetch('/api/send-email', {
                method: 'POST',
                headers: { 'Content-Type': 'application/json' },
                body: JSON.stringify(data)
              })
    
            
              this.email = ''
              this.agreed = false
    
              console.log('ok');
            } catch (error) {
              console.error(error);
              alert('Ошибка при отправке формы!');
            }
          }
        }
    
      }
      </script>
      
      <style scoped>


       .main-subscribe {
        position: relative;
        margin-top: 50px;
        max-width: 1920px;
        width: 100%;
        height: 500px;
      }
    
      .bg-color {
        position: absolute;
        width: 100%;
        height: 400px;
        background-color: #11442A;
        left: 0;
        bottom: 0;
    
      }
      .subscribe-content {
        position: absolute;
        display: flex;
        justify-content: space-between;
        margin: 0 auto;
        max-width: 1290px;
        width: 100%;
        height: 500px;
      }
    
      
      .subscribe-img {
        width: 550px;
        position: absolute;
        left: 0;
      }
      .subscribe-img img {
        object-fit: cover;
      }
      
      .subscribe-form {
        position: absolute;
        width: 100%;
        max-width: 630px;
    
        right: 0;
      }
      
      .form {
        font-family: 'maximacyrtcy_lighcomp';
        color: #fff;
        margin-top: 100px;
        padding: 67px 0;
        height: 400px;
        display: flex;
        flex-direction: column;
      }
    
      
      .form-row {
        display: flex;
        justify-content: space-between;
        align-items: flex-end;
        margin-bottom: 1rem;
      }
      .form-title {
        text-transform: uppercase;
        font-size: 52px;
        font-weight: 400;
    
      }
      .form-description {
        margin: 10px 0 40px;
        padding-right: 100px;
        letter-spacing: 0.025em;
        line-height: 25.2px;
        font-size: 18px;
      }
      label {
        display: block;
        margin-bottom: 0.5rem;
      }
    
      input[type="checkbox"] {
        margin-right: 0.5rem;
      }
    
      button {
        width: 190px;
        height: 60px;
        font-family: 'maximacyrtcy_lighcomp';
        color: #fff;
        text-transform: uppercase;
        font-size: 20px;
        letter-spacing: 0.025em;
        border: 1px solid #fff;
        background-color: transparent;
    
      }
      .main-checkbox {
        display: flex;
        color: rgba(249, 249, 242, 0.5);
      }
      .checkbox-container {
      display: inline-block;
    
    }
    
    .checkbox {
        margin-right: 10px;
      display: inline-flex;
      align-items: center;
      justify-content: center;
      width: 24px;
      height: 24px;
      border: 1px solid #FFF;
      background: transparent;
      cursor: pointer;
    }
    
    .checked {
      background: transparent;
    }
      #agree-label {
        color: rgb(249, 249, 242, 0.5);
        font-size: 16px;
        letter-spacing: 0.025em;
      }
    
      .custom-input {
      position: relative;
      width: 410px;
    }
    .custom-input input {
      border: none;
      background-color: transparent;
      width: 100%;
      padding-bottom: 10px;
      font-size: 16px;
      color: white;
      border-bottom: 1px solid white;
    }
    .custom-input input::placeholder {
      color: rgba(255, 255, 255, 0.5);
      font-family: 'maximacyrtcy_lighcomp';
        font-size: 16px;
        letter-spacing: 0.025em;
    }
    .custom-input:focus {
        outline: none;
    }
    
    @media (min-width:1366px) and (max-width:1399px) {
      .subscribe-content {
        width: 120px;
      }
      .form, .subscribe-form {
        width: 600px;
        left: 600px;
      }
      .custom-input {
        width: 390px;
      }
    }
    @media (min-width: 768px) and (max-width: 1365px) {
      .main-small {
        margin-top: 90px;
        width: 100%;
        min-width: 768px;
        max-width: 1365px;
      }
      .subscribe-content {
        position: relative;
        flex-direction: column;
        align-items: center;
        width: 100%;
        min-width: 748px;
        max-width: 1325px;
        background-color: #11442A;
    
      }
      .subscribe-content > div {
        position: relative;
        background-color: #11442A;
      }
      .subscribe-form {
        width: 768px;
        height: 370px;
      }
      .form {
        padding-top: 50px;
        margin: 0;
      }
      .subscribe-img {
        width: 100%;
        min-width: 768px;
        max-width: 1365px;
        height: 370px;
      }
      .subscribe-img img {
        height: 370px;
        width: 100%;
        object-fit: cover;
        object-position: center 100% ;
      }
    }
    @media (min-width: 360px) and (max-width: 767px) {
      .main-small {
        margin-top: 140px;
        width: 100%;
        min-width: 360px;
        max-width: 767px;
        height: 750px;
      }
      .subscribe-content {
        flex-direction: column;
        align-items: center;
        width: 100%;
        min-width: 320px;
        max-width: 737px;
        background-color: #11442A;
    
      }
      .subscribe-content > div {
        position: relative;
        background-color: #11442A;
      }
      .subscribe-form {
        width: 320px;
        height: 380px;
      }
      .form {
        padding-top: 30px;
        margin: 0;
      }
      .subscribe-img {
        width: 100%;
        min-width: 360px;
        max-width: 767px;
        height: 370px;
      }
      .subscribe-img img {
        height: 370px;
        width: 100%;
        object-fit: cover;
        object-position: center 100% ;
      }
      .form-title {
        font-size: 36px;
      }
      .form-description {
        padding: 0;
        font-size: 18px;
      }
      .form-row {
        flex-direction: column;
        width: 320px;
      }
      .custom-input {
        width: 320px;
      }
      input {
        width: 320px;
      }
      button .btn {
        margin: 20px 0 0;
        padding: 0 10px;
        min-width: 100%;
      }
      .main-checkbox {
        margin-bottom: 36px;
      }
    }
      </style>