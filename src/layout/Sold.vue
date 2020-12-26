<template>
    <Header @onSearch="onSearch($event)" />
    <Result :count="count" :books="allBooks" :soldBooks="soldBooks" />
</template>

<script>
import Header from "../components/HeaderSold";
import Result from "../components/ResultSold";
// import Info from "../components/Info";
import { ref, onMounted, computed } from "vue";
import axios from "axios";
export default {
    components: {
        Header,
        Result
    },
    props: {
        title: String
    },
    setup() {
        const counter = ref(1);
        const doubleCounter = computed(() => counter.value * 2);
        const updateCount = () => {
            counter.value++;
        };
        onMounted(updateCount);
        return {
            counter,
            doubleCounter
        };
    },
    data() {
        return {
            originData: [],
            visible: false,
            freeBooks: [],
            bookData: {},
            allBooks: 0,
            soldBooks: 0,
            count: 0,
            books: []
        }
    },
    created() {
        axios.get('https://book-charity-server.herokuapp.com/getBooks')
        // axios.get('http://localhost:3000/getBooks')
        .then((response) => {
            const data = response.data;
            this.freeBooks = data.filter((book) => {
                return book.p === 0;
            });
            const soldBooks = data.filter((book) => {
                this.count += book.p;
                return book.p !== 0;
            });
            this.allBooks = response.data.length;
            this.soldBooks = soldBooks.length;
            this.originData = [...this.freeBooks, ...soldBooks];
            this.books = this.originData;
        })
        .catch(function (error) {
            console.log(error);
        });
        this.originData = this.books;
    },
    methods: {
        onClose() {
            this.visible = false;
        },
        openModal(e) {
            this.visible = true;
            this.bookData = e;

        },
        onSearch(e) {
            this.filterBooks(e);
        },
        filterBooks(value) {
            if(!value) {
                this.books = this.originData;
            }
            this.books = this.originData.filter((book) => {
                return book.n.toLowerCase().indexOf(value.toLowerCase()) !== -1;
            });
        }
    }

}
</script>

<style>
body, html, #app {
    height: 100%;
}
</style>