<template>
  <div class="book" @click="openModal(bookData, bookId)">
        <div class="author text">{{bookData.a}}</div>
        <img :src="require('../assets/site_images/'+ bookId + '.jpg')" />
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
    width: 80%

}

.name {
    font-size: 20px;
    font-weight: 500;
    line-height: 26px;
}

.link {
    border-bottom: 1px solid #000;
    width: fit-content;
    padding-bottom: 10px;
    margin-top: 80px;
    cursor: pointer;
}

.link:hover {
    color: #A38970;
    border-bottom: 1px solid #A38970;
}

img {
    width: 230px;
    margin: 42px 0;
    cursor: pointer;
}

.book {
    width: 480px;
    padding: 20px;
}
@media only screen and (max-width: 840px) {
img {
    width: 60%;
}
.book {
    width: 95%;
    padding: 20px 10px;
}
.text {
        margin-left: 10%;
    }
    .link {
        margin-top: 40px;
        margin-left: 10%;
    }
}

@media only screen and (max-width: 400px) {
    .text {
        margin-left: 10%;
    }
    .link {
        margin-top: 40px;
        margin-left: 10%;
    }
}
</style>