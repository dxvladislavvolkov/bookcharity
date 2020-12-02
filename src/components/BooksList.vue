<template>
  <div>
    <h2 id="books">Каталог книг</h2>
    <Toolbar :filterData="filterData" @applyFilter="onApplyFilter($event)"></ToolBar>
    <div class="list-book">
        <div v-for="(book, index) in bookList" :key="index">
            <Book :bookData="book" :bookId="book.id + 1" @on-button-click="onClick($event)"/>
        </div>
    </div>
  </div>
</template>

<script>
import Book from "./Book";
import Toolbar from "./ToolBar";
export default {
    props: {
        books: Array,
        freeBooks: Array
    },
    data() {
        return {
            filteredBooks: [],
            normalizedBooks: [],
            filterData: {}
        }
    },
    created() {
        this.normalizedBooks = this.books;
        this.filteredBooks = this.freeBooks;
        let authors = new Set();
        let langs = new Set();
        let cities = new Set();
        this.filteredBooks.forEach((book) => {
            if(book.a && book.a !== " ") {
                authors.add(book.a);
            }
            if(book.l && book.l !== " ") {
                langs.add(book.l)
            }
            if(book.g && book.g !== " ") {
                cities.add(book.g)
            }
        });
        authors = [ ...authors ];
        langs = [ ...langs ];
        cities = [ ...cities ];
        this.filterData = { authors: authors.sort(), langs, cities };
    },
    watch: {
        books: {
            handler(val) {
                this.normalizedBooks = val;
            },
        deep: true
    },
    },
    computed: {
        bookList: function() {
            return this.normalizedBooks;
        }
    },
    components: {
        Toolbar,
        Book
    },
    methods: {
        onClick(e) {
            this.$emit("on-button-click", e)
        },
        onApplyFilter(e) {
            if(!e.checkedNames.length && !e.checkedLangs.length && !e.checkedCities.length) {
                this.normalizedBooks = this.books;
                return;
            }
            let books = this.filteredBooks;
            if(e.checkedNames && e.checkedNames.length) {
                books = books.filter((book) => {
                    return e.checkedNames.some(name => name === book.a);
                });
            }
            if(e.checkedCities && e.checkedCities.length) {
                books = books.filter((book) => {
                    return e.checkedCities.some(name => name === book.g);
                });
            }
            if(e.checkedLangs && e.checkedLangs.length) {
                books = books.filter((book) => {
                    return e.checkedLangs.some(name => name === book.l);
                });
            }
            this.normalizedBooks = books;
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

.list-book div{
    margin-bottom: 20px;
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