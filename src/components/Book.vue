<template>
  <div class="book">
      <img :src="image" />
      <h3 class="name">{{name}}</h3>
      <div class="author">{{author}}</div>
      <button type="button" @click="openModal(name, author)" class="btn btn-danger">Детали</button>
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
        name: String,
        author: String,
        image: String
    },
    components: {
    },
    methods: {
        openModal(name, author) {
            this.$emit("on-button-click", { name, author })
        }
    }

}
</script>

<style>
button {
  outline: none;
  margin-top: 5px;
}
img {
    width: 250px;
}

.book {
    padding: 20px;
}
@media only screen and (max-width: 600px) {
img {
    width: 350px;
}
}
</style>