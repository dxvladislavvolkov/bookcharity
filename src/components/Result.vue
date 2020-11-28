<template>
  <div class="result-container">
      <div>
          <span class="curency text">{{count}}</span><span class="undertext text">руб.</span>
          <div class="undertext text">собрано</div>
      </div>
  </div>
</template>

<script>
export default {
    props: {
        count: Number
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
    margin-bottom: 20px;
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
</style>