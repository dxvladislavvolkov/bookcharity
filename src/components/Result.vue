<template>
  <div class="result-container">
      <div>
          <span class="curency text">{{count}}</span><span class="undertext text">руб.</span>
          <div class="undertext text">собрано</div>
      </div>
      <div>
          <span class="curency text">{{books}}</span><span class="undertext text"></span>
          <div class="undertext text">всего книг</div>
      </div>
      <div>
          <span class="curency text">{{soldBooks}}</span><span class="undertext text"></span>
          <div class="undertext text">продано</div>
      </div>
  </div>
</template>

<script>
export default {
    props: {
        count: Number,
        books: Number,
        soldBooks: Number
    }

}
</script>

<style scoped>
.result-container {
    background-color: #F8F6F4;
    height: 205px;
    display: flex;
    justify-content: center;
    align-items: center;
    margin-top: 30px;
}

.result-container div {
    padding: 0px 25px;
}

.result-container div:nth-child(1) {
    border-right: 1px solid rgba(163, 137, 112, 0.6);
}

.result-container div:nth-child(2) {
    border-right: 1px solid rgba(163, 137, 112, 0.6);
}

.text {
    font-family: Montserrat;
    font-style: normal;
    font-weight: 400;
    letter-spacing: 0px;
    text-align: center;
    color: #282828;
}
.undertext {
    font-size: 18px;
}
.curency {
    font-size: 60px;
    line-height: 102px;
    letter-spacing: 0px;
}

@media only screen and (max-width: 670px) {
    .result-container {
        flex-direction: column;
        height: 100%;
        padding: 30px 0;
    }

    .result-container div:nth-child(1) {
        border-right: 0;
    }

    .result-container div:nth-child(2) {
        border-right: 0;
    }
}
</style>