<template>
    <div class="feedback">
        <div class="wrapper">
        <div class="review-form">
            <div class="review-form__title">Добавить свой отзыв</div>
            <div class="review-form__content">
                <div class="review-form__input-container">
                    <div class="custom-input">
                        <input type="name" id="name" v-model.trim="name" required placeholder="Имя">
                    </div>
                <div class="custom-input">
                    <input type="email" id="email" v-model.trim="email" required placeholder="Email">
                </div>
            </div>
            <div class="review-form__rating">
                <div class="rating-text">Оценка:</div>
                    <div class="rating-stars">
                        <img v-for="(star, index) in stars" :key="index"
                        :src="starImage(index)" @click="rate(index)" />
                    </div>
                </div>
                <div class="review-form__textarea-container">
                    <textarea v-model="reviewText" placeholder="Текст отзыва" class="review-form__textarea"></textarea>
                </div>
                <div class="review-form__submit-container">
                    <button @click="submitForm" :disabled="!isCheckboxChecked">Опубликовать</button>
                    <div class="main-checkbox">
                        <div class="checkbox-container" @click="toggleCheckbox">
                            <div :class="['checkbox', {'checked': isChecked}]" id="agree">
                                <svg v-if="isChecked" xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24">
                                    <path fill="#FFF" d="M9 16.2L4.8 12l-1.4 1.4 5.6 5.6L22.6 6.4l-1.4-1.4z"/>
                                </svg>
                            </div>
                        </div>
                    <label for="agree" class="agree-label">Даю согласие на обработку персональных данных</label>
                    </div>
                </div>
            </div>
        </div>
    </div>
</div>
</template>

<script>
    export default {
        data() {
            return {
                name: '',
                email: '',

                rating: 0,
                reviewText: '',
                isCheckboxChecked: false,
                isChecked: false,
                currentRating: 0,
                maxRating: 5,
                    starImages: [
                        require('../assets/icons/rating.png'),
                        require('../assets/icons/rating.png'),
                        require('../assets/icons/rating.png'),
                        require('../assets/icons/rating.png'),
                        require('../assets/icons/rating.png')
                        ],
                    ratedStarImages: [
                        require('../assets/icons/rating_add.png'),
                        require('../assets/icons/rating_add.png'),
                        require('../assets/icons/rating_add.png'),
                        require('../assets/icons/rating_add.png'),
                        require('../assets/icons/rating_add.png'),
                        ],
                    };
                },
            computed: {
                stars() {
                    return Array(this.maxRating).fill().map((_, index) => index + 1 <= this.currentRating);
                    },
                },
            methods: {
                toggleCheckbox() {
                    this.isChecked = !this.isChecked 
            },
                submitForm() {
                    if (!this.isCheckboxChecked) {
                    return;
                }

                const data = {
                    name: this.name,
                    email: this.email,
                    reviewText: this.reviewText,
                    rating: this.rating
                };

                fetch('/api/feedback', {
                    method: 'POST',
                    headers: {
                        'Content-Type': 'application/json'
                    },
                    body: JSON.stringify(data)
                })
                .then(response => {
                    if (!response.ok) {
                        throw new Error('Network response was not ok');
                    }
                    return response.json();
                })
                .then(data => {
                    console.log(data);
                })
                .catch(error => {
                    console.error('error!', error);
                });
            },
                rate(index) {
                    if (this.currentRating === index + 1) {
                        this.currentRating = 0;
                    } else {
                    this.currentRating = index + 1;
                    }
                },
                starImage(index) {
                    return this.stars[index] ? this.ratedStarImages[index] : this.starImages[index];
                }
            }
        }    
</script>
<style scoped>
.feedback {
    width: 100%;
    min-width: 1367px;
}
.wrapper {
    width: 1290px;
    margin: 0 auto;
}

.review-form {
    margin-top: 70px;
    margin-left: 0;
    width: 741px;
    height: 434px;
    display: flex;
    flex-direction: column;
    align-items: flex-start;
}
.review-form__title {
    font-family: 'maximacyrtcy_lighcomp';
    font-size: 36px;
    text-transform: uppercase;
    color: #333934;
}
.review-form__input-container {
    margin-top: 40px;
    display: flex;
    align-items: flex-end;
}
.custom-input {
    position: relative;
    width: 355px;
}
.custom-input:first-child {
    margin-right: 30px;
}
.custom-input input {
    border: none;
    background-color: transparent;
    width: 100%;
    padding-bottom: 10px;
    font-size: 16px;
    color: #70756E;
    border-bottom: 1px solid #DAD7CD;
    letter-spacing: 0.025em;
    font-family: 'maximacyrtcy_lighcomp';
    outline: none;
}
.custom-input:focus {
    outline: none;
}
.review-form__rating {
    margin-top: 40px;
    display: flex;
    width: 186px;
    justify-content: space-between;
    align-items: center;
}
.rating-text {
    margin-right: 20px;
    font-family: 'maximacyrtcy_lighcomp';
    font-size: 18px;
    color: #333934;
    padding-bottom: 5px;
}
.review-form__textarea {
    margin-top: 30px;
    width: 740px;
    height: 72px;
}
textarea {
    resize: none;
    border-bottom: 1px solid #DAD7CD;
    border-top: none;
    border-left: none;
    border-right: none;
    font-family: 'maximacyrtcy_lighcomp';
    font-size: 18px;
    color: #70756E !important;
    background-color: transparent;
    outline: none;
}
.review-form__submit-container {
    display: flex;
    flex-direction: column;
    align-items: start;
}
button {
    margin-top: 40px;
    width: 299px;
    height: 61px;
    font-size: 20px; 
    background-color: transparent;
    font-family: 'maximacyrtcy_lighcomp';
    text-transform: uppercase;
    color: #333934;
    letter-spacing: 0.025em;
    border: 1px solid #333934;
    cursor: pointer;
}
.main-checkbox {
    margin-top: 20px;
    display: flex;
    color: rgba(249, 249, 242, 0.5);
}
.checkbox-container {
    display: inline-block;
    width: 34px;
    height: 28px;
}
.checkbox {
    margin-right: 10px;
    display: inline-flex;
    align-items: center;
    justify-content: center;
    width: 24px;
    height: 24px;
    border: 1px solid #70756E;
    cursor: pointer;
    background-color: transparent;
}
.checked {
    width: 24px;
    height: 24px;
    background-color: #11442A;
}
.agree-label {
    padding-top: 2px;
    font-family: 'maximacyrtcy_lighcomp';
    color: #70756E;
    font-size: 16px;
    letter-spacing: 0.025em;
}
@media (min-width: 768px) and (max-width: 1366px) {
    .feedback {
        padding-left: 34px;
        width: 100%;
        min-width: 768px;
    }
    .wrapper {
        width: 100%;
        min-width: 700px;
    }
    .review-form {
        width: 700px;
    }
    .custom-input {
        width: 340px;
    }
    .custom-input:first-child {
        margin-right: 20px;
    }
    .review-form__textarea-container, 
    .review-form__textarea {
        width: 700px !important;
    }
}
@media (min-width: 360px) and (max-width: 767px) {
    .feedback {
        padding-left: 20px;
        width: 100%;
        min-width: 360px;
    }
    .wrapper {
        width: 100%;
        min-width: 320px;
    }
    .review-form {
        padding-right: 20px;
        width: 100%;
        min-width: 320px;
        height: 465px;
    }
    .review-form__content {
        width: 100%;
        min-width: 320px;
    }
    .review-form__input-container {
        flex-direction: column;
        align-items: flex-start;
    }
    .custom-input {
        width: 100%;
        min-width: 320px;
    }
    .custom-input:first-child {
        margin-right: 0;
    }
    .review-form__textarea-container, 
    .review-form__textarea {
        width: 100%;
        min-width: 319px !important;
    }
}
</style>
  