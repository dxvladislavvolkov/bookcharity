<template>
  <div id="header">
    <div class="header-container">
        <img class="header-item" src="../assets/BookCharity.svg">
        <Search class="header-item" />
    </div>
  </div>
</template>

<script>
import Search from "./Search";
export default {
    components: {
        Search
    }

}
</script>

<style>
    #header {
        background-color: #fff;
        width: 100%;
        height: 15%;
    }

    .header-container {
        display: flex;
        flex-direction: row;
        flex-wrap: wrap;
        justify-content: space-between;
        margin: 0 auto;
        width: 80%;
        min-width: 600px;
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