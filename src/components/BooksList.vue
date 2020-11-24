<template>
  <div>
    <h2>Каталог книг</h2>
    <div class="list-book">
        <div v-for="(book, index) in books" :key="index">
            <Book :name="book.name" :author="book.author" :image="book.image" @on-button-click="onClick($event)"/>
        </div>
    </div>
  </div>
</template>

<script>
import Book from "./Book";
export default {
    props: {
        books: Array
    },
    components: {
        Book
    },
    methods: {
        onClick(e) {
            this.$emit("on-button-click", e)
        }
    }

}
</script>

<style scoped>
.list-book {
    display: flex;
    flex-direction: row;
    flex-wrap: wrap;
    justify-content: center;
    min-width: 600px;
    margin: 0 auto;
}

h2 {
    font-family: Montserrat;
    font-size: 40px;
    font-style: normal;
    font-weight: 700;
    line-height: 52px;
    letter-spacing: 0px;
    text-align: left;
    margin-left: 10%;
    margin-top: 60px;
    margin-bottom: 80px;
}

@media only screen and (max-width: 840px) {
    .list-book {
        flex-direction: column;
        flex-wrap: nowrap;
        min-width: 280px;
        width: 100%;
    }
    h2 {
        text-align: center;
        margin-left: 0;
    }
}
</style>