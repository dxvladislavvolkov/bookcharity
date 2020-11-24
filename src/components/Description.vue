<template>
    <div class="description-container">
        <div class="description-text">
            <div>СТАРТ 29 НОЯБРЯ</div>
            <h2>Благотоворительная распродажа книг</h2>
            <p>Вы покупаете книгу в отличном состоянии по цене, которую выбираете сами + делаете доброе дело и спасаете жизни.</p>
            <button type="button" class="btn btn-secondary">Перейти к книгам</button>
        </div>
        <div class="image-container">
            <div class="image"></div>
        </div>
    </div>
</template>

<script>
export default {

}
</script>

<style scoped>
.image-container {
    flex: 2;
}
.image {
    background-image: url("../assets/description-image.png");
    width: 100%;
    height: 100%;
    background-repeat: no-repeat;
    background-size: cover;
}
.description-container {
    background-color: #F1EDE9;
    display: flex;
    flex-wrap: wrap;
    flex-direction: row;
    justify-content: space-between;
}

.description-text {
    flex: 1;
    padding-left: 10%;
    padding-right: 10%;
    padding-top: 80px;
    text-align: left;
}

.description-text div {
    font-family: Montserrat;
    font-size: 16px;
    font-style: normal;
    font-weight: 600;
    line-height: 20px;
    letter-spacing: 0.05em;
    text-align: left;

}

.description-text h2 {
    font-family: Montserrat;
    font-size: 46px;
    font-style: normal;
    font-weight: 600;
    line-height: 56px;
    letter-spacing: 0.02em;
    text-align: left;

}

.description-text p {
    font-family: Montserrat;
    font-size: 18px;
    font-style: normal;
    font-weight: 400;
    line-height: 28px;
    letter-spacing: 0.02em;
    text-align: left;

}

.btn {
    width: 240px;
    height: 56px;
    font-family: Montserrat;
    font-size: 16px;
    font-style: normal;
    font-weight: 700;
    line-height: 20px;
    letter-spacing: 0.02em;
    margin-top: 15px;
    margin-bottom: 80px;
}

.btn-secondary, .btn-secondary:hover, .btn-secondary:active, .btn-secondary:visited {
    background-color: #A38970 !important;
    color: #fff;
}

@media only screen and (max-width: 840px) {
.description-container {
    flex-direction: column-reverse;
    justify-content: center;
}
.description-text {
    padding-left: 0;
    padding-top: 80px;
    padding-right: 0;
    text-align: center;
    margin: 0 auto;
    width: 80%;
}
.description-text div {
    text-align: center;

}

.description-text h2 {
    text-align: center;
    font-size: 24px;
    line-height: 35px;
}

.description-text p {
    text-align: center;

}
.btn {
    width: 100%;
    margin-top: 20px;
    margin-bottom: 80px;
}
}
@media only screen and (max-width: 770px) {
    .description-text {
        padding-top: 60px;
    }

    .btn {
        margin-bottom: 60px;
    }
}
@media only screen and (max-width: 280px) {
    .description-text h2 {
        text-align: center;
        font-size: 20px;
        line-height: 35px;
    }

    .description-text p {
        font-size: 16px;
    }
}

</style>