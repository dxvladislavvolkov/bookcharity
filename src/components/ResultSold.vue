<template>
  <div class="result-container">
      <div class="result">
          <span class="curency text">{{count}}</span><span class="undertext text">руб.</span>
          <div class="undertext text">собрано</div>
      </div>
      <div class="result">
          <span class="curency text">{{soldBooks}}</span><span class="undertext text"></span>
          <div class="undertext text">продано книг</div>
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
    height: 100%;
    margin-top: 55px;
}

.result {
    display: inline-block;
}

.result-container div {
    padding: 0px 25px;
}

.result-container div:nth-child(1) {
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
}
</style>