<template>
  <div class="rules">
      <h2>Принцип распродажи</h2>
      <div class="rules-description">
          <div>
            <img src="../assets/kitty.png" />
          </div>
          <div class="text">
              <div>
                <p>Принцип её заключается в том, что мы продаём прочитанные книги за ту стоимость, которую ВЫ считаете для себя приемлемой. Все деньги, полученные с продаж, переводим на счет двух приютов для бездомных животных <b class="link" @click="onClick('https://vk.com/saved_to_live')">"Спасённые, чтобы жить"</b> и <b class="link" @click="onClick('https://vk.com/club189884687')">"Зверополис"</b>.</p>
                <p>Для того чтобы купить книгу, вам необходимо написать название книги <b class="link" @click="onClick('https://www.instagram.com/maggvlk/')">@maggvlk</b>. После совершения оплаты вы связываетесь с продавцом напрямую, чтобы договориться о месте передачи книге или деталях получения. Просим обратить Ваше внимание, что часть книг находятся в разных городах, из-за чего необходимо учитывать стоимость доставки, которая дополнительно оплачивается Вами.</p>
              </div>
              <button type="button" class="btn btn-secondary" @click="onClick('https://www.instagram.com/maggvlk/')">Написать @maggvlk</button>
          </div>
      </div>
  </div>
</template>

<script>
export default {
    methods: {
        onClick(link) {
            window.open(link);
        }
    }
}
</script>

<style scoped>
.link {
    cursor: pointer;
}
.rules {
    margin-left: 10%;
}
.rules-description {
    display: flex;
    flex-wrap: wrap;
    flex-direction: row;
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
    text-align: left;;
    margin-left: 80px;
    margin-top: 20px;
}

.text div {
    max-width: 655px;
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
@media only screen and (max-width: 1400px) {
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
@media only screen and (max-width: 430px) {
    .text {
        padding: 0 10px;
    }

    p {
        margin: 0 0 20px;
    }
    .text div {
        margin: 0 10px;
    }
}
</style>