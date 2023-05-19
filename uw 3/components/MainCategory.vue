<template>
    <div class="main-category">
        <div class="container">
            <div class="row">
                <div class="col-12">
                    <div class="title">ВЫБРАТЬ ПО КАТЕГОРИЯМ</div>
                    <div class="category-container">
                    <div class="category">
                        <img src="../assets/images/category/category_1.png" alt="Body" />
                        <span class="category-name">Боди</span>
                    </div>
                    <div class="category">
                        <img src="../assets/images/category/category_2.png" alt="Pajamas" />
                        <span class="category-name">ПИЖАМЫ</span>
                    </div>
                    <div class="category">
                        <div class="vertical-container">
                        <img src="../assets/images/category/category_3.png" alt="Panties" />
                        <span class="category-name">ТРУСИКИ</span>
                    </div>
                    <router-link to="/example"><button class="view-all-button">СМОТРЕТЬ ВСЕ КАТЕГОРИИ</button></router-link>
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
    name: "MainCategory",
};
</script>

<style scoped>
.title {
    margin-bottom: 50px;
    font-family: 'maximacyrtcy_lighcomp';
    text-transform: uppercase;
    color: #333934;
    font-size: 52px;
    letter-spacing: 0.025em;
    text-align: left;
}
@media (min-width: 360px) and (max-width: 767px) {

    .title {
        font-size: 30px;
        margin-bottom: 0;
}
}
.main-category {
    margin: 100px auto 0;
    width: 1290px;
    height: 642px;
}
@media (max-width: 1366px) {
        .main-category {
        width: 100%;
        max-width: 1290px;
    }
}
@media (max-width: 768px) {
    .main-category {
        width: 100%;
        max-width: 700px;
    }
}
@media (min-width: 360px) and (max-width: 767px) {
    .main-category {
        width: 100%;
        min-width: 320px;
        height: 926px;
    }
}
.category-container {
    display: flex;
    justify-content: space-between;
    height: 510px;
}
@media (min-width: 360px) and (max-width: 767px) {
    .category-container {
        flex-direction: column;
    }
}
.category {
    position: relative;
    width: calc(33.33% - 20px);
    height: 510px;
    height: 510px;
    object-fit: cover;
}
.category:last-child {
    height: 290px;
}
.category:nth-child(2) {
    margin-top: 30px;
}
@media (max-width: 768px) {
    .category {
        width: calc(33% - 10px);
    }
}
@media (min-width: 360px) and (max-width: 767px) {

    .category {
        width: 100%;
        height: 250px;
        margin-top: 20px;
    }
    .category .vertical-container {
      height: 250px;
    }
}
.vertical-container {
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    height: 100%;
}
@media (min-width: 360px) and (max-width: 767px) {
.vertical-container {
    height: 250px;
}
}

.category img {
    width: 100%;
    height: 100%;
    object-fit: cover;
}

.category-name {
    position: absolute;
    top: 10px;
    left: 20px;
    font-family: 'maximacyrtcy_lighcomp';
    text-transform: uppercase;
    font-size: 52px;
    color: #fff;
}
@media (min-width: 360px) and (max-width: 767px) {
    .category-name {
        font-size: 30px;
    }
}
.view-all-button {
    width: 100%;
    max-width: 410px;
    height: 60px;
    font-size: 20px; 
    margin-top: 18px;
    padding: 10px 20px;
    background-color: transparent;
    font-family: 'maximacyrtcy_lighcomp';
    text-transform: uppercase;
    color: #333934;
    letter-spacing: 0.025em;
    border: 1px solid #333934;
    cursor: pointer;
    }


@media (min-width: 360px) and (max-width: 767px) {

    .view-all-button {
        min-width: 100%;
    }
}
</style>
