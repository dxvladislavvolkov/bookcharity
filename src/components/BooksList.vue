<template>
  <div class="list-book">
      <div v-for="(book, index) in books" :key="index">
          <Book :name="book.name" :author="book.author" :image="book.image" @on-button-click="onClick()"/>
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

<style>
.list-book {
    display: flex;
    flex-direction: row;
    flex-wrap: wrap;
    justify-content: center;
    width: 70%;
    min-width: 600px;
    margin: 0 auto;
}

@media only screen and (max-width: 600px) {
    .list-book {
        flex-direction: column;
        min-width: 320px;
        width: 100%;
    }
}
</style>