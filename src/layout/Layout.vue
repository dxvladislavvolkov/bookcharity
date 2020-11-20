<template>
    <Header />
    <!-- <ModalWindow :visible="visible" /> -->
    <Description />
    <BooksList :books="books" @onButtonClick="openModal" />
</template>

<script>
import Header from "../components/Header";
import BooksList from "../components/BooksList";
// import ModalWindow from "../components/ModalBook";
import Description from "../components/Description";
import { ref, onMounted, computed } from "vue";
export default {
    components: {
        Header,
        BooksList,
        Description
        // ModalWindow
    },
    props: {
        title: String
    },
    setup(props) {
        const counter = ref(1);
        const doubleCounter = computed(() => counter.value * 2);
        console.log(props);
        const updateCount = () => {
            counter.value++;
        };

        // watch(counter, (newValue) => {
        //     doubleCounter.value = newValue * 2;
        // })

        onMounted(updateCount);
        return {
            counter,
            doubleCounter,
            books: [
                {
                    name: "Маленький принц",
                    author: "Антуан де Сент-Экзюпери",
                    image: require("../assets/book.jpg")
                }, {
                    name: "Маленький принц",
                    author: "Антуан де Сент-Экзюпери",
                    image: require("../assets/book.jpg")
                }, {
                    name: "Маленький принц",
                    author: "Антуан де Сент-Экзюпери",
                    image: require("../assets/book.jpg")
                }, {
                    name: "Маленький принц",
                    author: "Антуан де Сент-Экзюпери",
                    image: require("../assets/book.jpg")
                }, {
                    name: "Маленький принц",
                    author: "Антуан де Сент-Экзюпери",
                    image: require("../assets/book.jpg")
                }, {
                    name: "Маленький принц",
                    author: "Антуан де Сент-Экзюпери",
                    image: require("../assets/book.jpg")
                }, {
                    name: "Маленький принц",
                    author: "Антуан де Сент-Экзюпери",
                    image: require("../assets/book.jpg")
                }, {
                    name: "Маленький принц",
                    author: "Антуан де Сент-Экзюпери",
                    image: require("../assets/book.jpg")
                }, {
                    name: "Маленький принц",
                    author: "Антуан де Сент-Экзюпери",
                    image: require("../assets/book.jpg")
                }
            ]
        };
    },
    data() {
        return {
            visible: false
        }
    },
    methods: {
        openModal() {
            this.visible = true;

        },
        count() {
            this.counter++;
        }
    }

}
</script>

<style>

</style>