<template>
  <div id="header">
    <div class="header-container">
        <img class="header-item" src="../assets/BookCharity.svg">
        <h2>Распродажа завершена</h2>
    </div>
  </div>
</template>

<script>
export default {
}
</script>

<style>
    #header {
        background-color: #fff;
        width: 100%;
        /* height: 15%; */
    }

    .header-container {
        margin: 0 auto;
        align-items: center;
    }

    .header-container img {
        width: 330px;
        margin-top: 10px;
        margin-bottom: 10px;
    }

    .header-item {
        /* flex: 1; */
    }

    .header-item:nth-child(2) {
        margin-top: 16px;
        /* margin-left: 20px; */
        width: 50%;
        max-width: 550px;
    }

@media only screen and (max-width: 840px) {
    .header-container {
        flex-direction: column;
        width: 100%;
        min-width: 280px;
    }
    .header-item:nth-child(2) {
        margin: 16px 0 20px 0;
    }

    .header-item:nth-child(2) {
        width: 90%;
    }

    .header-container img {
        width: 90%;
    }
}

@media only screen and (max-width: 320px) {
    .header {
        padding: 0 10px;
    }
}
</style>