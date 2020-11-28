<template>
  <div class="book" v-bind:class="{ 'book-sold': bookData.p !== 0 }" @click="openModal(bookData, bookId)">
        <div class="author text">№{{bookData.id + 1}} {{bookData.a}}</div>
        <div class="image-container">
            <img :src="require('../assets/site_images/'+ bookId + '.jpg')" />
        </div>
        <p class="name text">{{bookData.n}}</p>
      <div v-if="bookData.p === 0" class="link" @click="openModal(bookData, image)">Посмотреть<i class="arrow fas fa-long-arrow-alt-right"></i></div>
      <p v-if="bookData.p !== 0" class="sold">Куплена</p>
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
            if(bookData.p === 0) {
                this.$emit("on-button-click", { bookData, bookId })
            }
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
  transform: scale(1.02);
  opacity: 0.8;
}

.book:not(:hover) {
  transition: 1s;
  transform: scale(1);
  opacity: 1;
}

.book-sold {
    opacity: 0.6;
}

.book-sold:first-child:hover{
    transition: 0s;
    transform: scale(1);
    opacity: 0.6;
}

.book-sold:not(:hover) {
  transition: 0s;
  transform: scale(1);
  opacity: 0.6;
}

.book-sold img {
  cursor: auto;
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
    margin-bottom: 5px;
    cursor: pointer;
}

.sold {
   color: #A38970;
   margin-bottom: 5px;
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
    background-color: #F8F6F4;
    width: 410px;
    padding: 20px;
    margin: 0 5px;
    margin-bottom: 15px;
}
@media only screen and (max-width: 840px) {

.book {
    width: 90%;
    padding: 20px 10px;
    margin: 0 auto;
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
    .book {
        width: 100%;
    }
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