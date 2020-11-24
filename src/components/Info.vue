<template>
  <div class="info">
      <div class="info-item">
          <div class="name">Выгода</div>
          <div class="desc">книга в отличном состоянии</div>
      </div>
      <div class="info-item">
          <div class="name">29 ноября</div>
          <div class="desc">дата старта</div>
      </div>
      <div class="info-item">
          <div class="name">Помощь</div>
          <div class="desc">бездомным животным</div>
      </div>
  </div>
</template>

<script>
export default {

}
</script>

<style scoped>
.info-item {
    width: 260px;
    margin: 80px 2%;
}
.info {
    display: flex;
    flex-direction: row;
    flex-wrap: wrap;
    justify-content: center;
    align-content: center;
}

.info .name {
    font-family: Montserrat;
    font-size: 30px;
    font-style: normal;
    font-weight: 400;
    line-height: 40px;
    letter-spacing: 0em;
    text-align: center;
    padding-bottom: 8px;
    border-bottom: 1px solid #A38970;
}

.info .desc {
    font-family: Montserrat;
    font-size: 18px;
    font-style: normal;
    font-weight: 400;
    line-height: 24px;
    letter-spacing: 0em;
    text-align: center;
    padding-top: 12px;
}
@media only screen and (max-width: 905px) {
    .info-item {
        margin: 60px 10px;
    }
}
@media only screen and (max-width: 860px) {
    .info-item {
        margin: 60px 5px;
    }
}

@media only screen and (max-width: 840px) {
    .info-item {
        margin: 30px 0;
    }
    .info {
        flex-direction: column;
        justify-content: center;
    }
}

</style>