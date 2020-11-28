<template>
  <div class="book" @click="openModal(bookData, bookId)">
        <div class="author text">{{bookData.a}}</div>
        <div class="image-container">
            <img :src="require('../assets/site_images/'+ bookId + '.jpg')" />
        </div>
        <p class="name text">{{bookData.n}}</p>
      <div class="link" @click="openModal(bookData, image)">Посмотреть<i class="arrow fas fa-long-arrow-alt-right"></i></div>
  </div>
</template>

<script>
export default {
    data() {
        return {
            visible: false
        }
    },
    props: {
        bookData: Object,
        bookId: Number
    },
    components: {
    },
    methods: {
        openModal(bookData, bookId) {
            this.$emit("on-button-click", { bookData, bookId })
        }
    }

}
</script>

<style scoped>
.arrow {
    margin-left: 10px;
}

.book:first-child:hover  {
  transition: 1s;
  transform: scale(1.01);
  opacity: 0.8;
}

.book:not(:hover) {
  transition: 1s;
  transform: scale(1);
  opacity: 1;
}

.text {
    font-family: Montserrat;
    font-style: normal;
    letter-spacing: 0px;
    text-align: left;
    color: #A38970;
    margin-left: 42px;
}
.author {
    font-size: 28px;
    font-weight: 500;
    line-height: 36px;
    width: 80%;
    min-height: 95px;
}

.image-container {
    width: 160px;
    height: 290px;
    margin: 0px auto 20px auto;
}

.name {
    font-size: 20px;
    font-weight: 500;
    line-height: 26px;
    min-height: 78px;
}

.link {
    border-bottom: 1px solid #000;
    width: fit-content;
    margin-bottom: 10%;
    cursor: pointer;
}

.link:hover {
    color: #A38970;
    border-bottom: 1px solid #A38970;
}

img {
    width: 160px;
    cursor: pointer;
}

.book {
    width: 410px;
    padding: 20px;
}
@media only screen and (max-width: 840px) {

.book {
    width: 95%;
    padding: 20px 10px;
}
.text {
        margin-left: 10%;
    }
.link {
    margin-top: 0;
    margin-left: 10%;
}
}

@media only screen and (max-width: 500px) {
    img {
        width: 60%;
    }
    .author {
        min-height: auto;
    }

    .image-container {
        margin: 42px auto;
        width: 100%;
        height: 100%;
    }
}

@media only screen and (max-width: 400px) {
    .text {
        margin-left: 10%;
    }
    .link {
        margin-top: 0;
        margin-left: 10%;
    }
}
</style>