<template>
    <div id="search">
        <input type="text" placeholder="Введите название книги" @keyup.enter="onClick(searchValue)" class="form-control form-control-sm search" v-model="searchValue" />
        <input class="btn btn-secondary" type="button" value="Найти" @click="onClick(searchValue)"/>
    </div>
</template>

<script>
export default {
    data() {
        return {
            searchValue: ""
        }
    },
    methods: {
        onClick(value) {
            this.$emit("on-search", value);
            let slide = document.getElementById("books");
            let top = window.scrollY + slide.getBoundingClientRect().y;
            window.scrollTo({
                top: top,
                behavior: "smooth"
            });
        },
    }
}
</script>

<style scoped>
#search {
    display: flex;
}
.search {
    border-radius: 3px 0px 0px 3px;
    height: 56px;
    flex: 3;
    border: 1px solid #A38970;

    font-family: Montserrat;
    font-size: 16px;
    font-style: normal;
    font-weight: 400;
    line-height: 20px;
    letter-spacing: 0.02em;
    color: #A38970;
}
.btn {
    flex: 1;
    border-radius: 0px 3px 3px 0px;
    background-color:#A38970;
    color: #fff;
    font-family: Montserrat;
    font-size: 16px;
    font-style: normal;
    font-weight: 700;
    line-height: 20px;
    letter-spacing: 0.02em;
    height: 56px;
}
</style>