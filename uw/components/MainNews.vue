<template>
    <div class="main-news">
        <div class="container">
            <div class="row">
                <div class="col-12">
                    <div class="title">Наши новости</div>
                    <div class="news-container">
                    <div class="new">
                        <img src="../assets/images/news/new_1.png" alt="new_1" />
                        <span class="new-date">15 марта 2023</span>
                        <span class="new-description">3 Лучших ЭКО-стиля для больших бюстов</span>
                    </div>
                    <div class="new">
                        <img src="../assets/images/news/new_2.png" alt="new_2" />
                        <span class="new-date">26 Февраля 2023</span>
                        <span class="new-description">Будущее моды: вместе мы делаем ее лучше</span>
                    </div>
                    <div class="new">
                        <div class="vertical-container">
                            <img src="../assets/images/news/new_3.png" alt="new_3" />

                            <span class="new-date">10 Февраля 2023</span>
                            <span class="new-description">эко-вещи из переработанных материалов</span>


                    </div>
                        <button class="view-all-button">Перейти в блог</button>
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
    name: "MainNews",
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
.main-news {
    margin: 100px auto 0;
    width: 1290px;
    height: 702px;
}
@media (max-width: 1366px) {
        .main-news {
            margin-top: 900px;
        width: 100%;
        max-width: 1290px;
    }
}
@media (max-width: 768px) {
    .main-news {
        width: 100%;
        max-width: 700px;
    }
}
@media (min-width: 360px) and (max-width: 767px) {
    .main-news {
        margin-top: 100px;
        width: 100%;
        min-width: 320px;
        height: 1226px;
    }
}
.news-container {
    display: flex;
    justify-content: space-between;
    width: 100%;
    max-width: 1290px;
    height: 510px;
}
@media (min-width: 360px) and (max-width: 767px) {
    .news-container {
        height: 1226px;

        flex-direction: column;
        justify-content: space-around;
    }
}
.new {
    display: flex;
    flex-direction: column;
    width: calc(33.33% - 18px);
    height: 590px;
    object-fit: cover;
}
.new:last-child {
    height: 290px;
}

@media (max-width: 768px) {
    .new {
        width: calc(33% - 10px);
    }
}
@media (min-width: 360px) and (max-width: 767px) {

    .new {
        width: 100%;
        height: 350px;
        margin-top: 20px;
    }
    .new img {

        max-height: 330px;
    }
}
.vertical-container {
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    height: 590px;
}
@media (min-width: 360px) and (max-width: 767px) {

    .new .vertical-container img {
        height: 300px;

}
}
.new img {
    width: 98%;
    height: 500px;
    object-fit: cover;
}
.new:last-child img {
    height: 410px;
}
.new-date, .new-description {
    margin-top: 20px;
    font-family: 'maximacyrtcy_lighcomp';
    color: #333934; 
}
.new-date {
    font-size: 16px;
}
.new-description {
    font-size: 24px;
    text-transform: uppercase;
}
@media (min-width: 360px) and (max-width: 767px) {
    .main-news {
        height: 1500px;
    }
    .new-date, .new-description  {
        font-size: 30px;
    }
    .new-date {
        font-size: 16px;
    }
    .new-description {
        font-size: 20px;
    }
}
.view-all-button {
    width: 100%;
    max-width: 410px;
    height: 60px;
    font-size: 20px; 
    margin-top: 30px;
    padding: 20px 20px;
    background-color: transparent;
    font-family: 'maximacyrtcy_lighcomp';
    text-transform: uppercase;
    color: #333934;
    letter-spacing: 0.025em;
    border: 1px solid #333934;
    cursor: pointer;
    }



</style>
