<template>
  <div class="rules">
      <h2>Принцип распродажи</h2>
      <div class="rules-description">
          <div>
            <img src="../assets/kitty.png" />
          </div>
          <div class="text">
              <div>
                <p>Принцип её заключается в том, что @maggvlk продаёт книги, которые прочитала и и не захотела оставлять в своей библиотеке, за ту стоимость, которую ВЫ посчитаете достойной. Все деньги, полученные с продаж, она переведёт  в котятский приют <b>@spasionnye</b> . В прошлый раз мы собрали около <b>9000₽</b>!</p>
                <p>Если вы желаете принять участие, предоставив безвозмездно собственные книги на продажу в помощь котикам, напишите ей об этом в Директ. Из других городов тоже можно!</p>
              </div>
              <button type="button" class="btn btn-secondary" @click="onClick">Написать @maggvlk</button>
          </div>
      </div>
  </div>
</template>

<script>
export default {
    methods: {
        onClick() {
            window.open("https://www.instagram.com/maggvlk/");
        }
    }
}
</script>

<style scoped>
.rules {
    margin-left: 10%;
}
.rules-description {
    display: flex;
    flex-wrap: wrap;
    flex-direction: row;
}
p {
    width: 610px;
}
h2 {
    font-family: Montserrat;
    font-size: 40px;
    font-style: normal;
    font-weight: 700;
    line-height: 52px;
    letter-spacing: 0px;
    text-align: left;
    margin-bottom: 42px;
}
.btn-secondary, .btn-secondary:hover, .btn-secondary:active, .btn-secondary:visited {
    background-color: #A38970 !important;
    color: #fff;
}
.text {
    font-family: Montserrat;
    font-size: 18px;
    font-style: normal;
    font-weight: 400;
    line-height: 31px;
    letter-spacing: 0px;
    text-align: left;
    margin-left: 60px;
    margin-top: 20px;
}

.text div {
    max-width: 610px;
}
.btn {
    width: 240px;
    height: 56px;
    height: 56px;
    width: 240px;
    left: 692px;
    top: 1332px;
    border-radius: 3px;

    font-family: Montserrat;
    font-size: 16px;
    font-style: normal;
    font-weight: 700;
    line-height: 20px;
    letter-spacing: 0.02em;
    margin-top: 30px;

}

@media only screen and (max-width: 1330px) {
    p {
        width: 550px;
    }
}
@media only screen and (max-width: 1265px) {
    p {
        max-width: 610px;
        text-align: center;
        width: 100%
    }
    h2 {
        margin-left: 0;
        text-align: center;
    }
    .rules {
        margin-left: 0;
    }
    .rules-description {
        flex-direction: column;
        justify-content: center;
        flex-wrap: nowrap;
    }
    .text {
        margin-left: 0;
        text-align: center;
    }
    .text div {
        margin: 0 auto;
    }

}
@media only screen and (max-width: 840px) {
    img {
        width: 80%;
    }
}
@media only screen and (max-width: 400px) {
    .text {
        padding: 0 10px;
    }

    p {
        margin: 0 0 20px;
    }
    .text div {
        margin: 0 5px;
    }
}
</style>