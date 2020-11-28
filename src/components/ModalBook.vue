<template>
  <div class="modal-content" v-if="visible">
    <div class="header">
      <i class="custom-icon fas fa-times fa-lg" @click="onClose"></i>
    </div>
    <div class="modal-body">
      <div class="title text">{{data.bookData.a}}</div>
      <div class="name text">{{data.bookData.n}}</div>
      <div class="image-container">
        <img :src="require('../assets/state/'+ data.bookId + '.jpg')" />
      </div>
      <div class="additions">
        <div>Обложка: {{data.bookData.c}}</div>
        <div>Состояние: {{data.bookData.s}}</div>
        <div>Язык: {{data.bookData.l}}</div>
        <div>Город: {{data.bookData.g}}</div>
      </div>
      <button type="button" class="btn btn-secondary" @click="onClick">Написать @maggvlk</button>
    </div>
  </div>
</template>

<script>
export default {
    props: {
        visible: Boolean,
        data: Object
    },
    methods: {
      onClose() {
        this.$emit("close-modal", true);
      },
      onClick() {
            window.open("https://www.instagram.com/maggvlk/");
        }
    }
}
</script>

<style scoped>
.modal-content {
    z-index: 1001;
    width: 760px;
    position: fixed;
    left: 50%;
    top: 50%;
    -ms-transform: translate(-50%,-50%);
    -moz-transform:translate(-50%,-50%);
    -webkit-transform: translate(-50%,-50%);
    transform: translate(-50%,-50%);
}

.additions div{
  margin-top: 5px;
}

.modal-content .header {
  text-align: right;
  padding: 20px;
}

.additions {
    width: 280px;
    margin: 0 auto;
    text-align: left;
    padding-left: 20px;
    padding-top: 20px;
}

i {
  cursor: pointer;
}

img {
  width: 280px;
  margin-top: 25px;
}

.image-container {
  min-height: 373px;
}

.text {
  font-family: Montserrat;
  text-align: center;
  letter-spacing: 0px;
  font-weight: 500;
  font-style: normal;
}

.title {
  font-size: 28px;
  line-height: 36px;
}

.name {
  font-size: 18px;
  line-height: 23px;
}

.btn-secondary, .btn-secondary:hover, .btn-secondary:active, .btn-secondary:visited {
    background-color: #A38970 !important;
    color: #fff;
}
.btn {
    width: 240px;
    height: 56px;
    height: 56px;
    width: 240px;
    left: 692px;
    top: 1332px;
    border-radius: 3px;

    font-family: Montserrat;
    font-size: 16px;
    font-style: normal;
    font-weight: 700;
    line-height: 20px;
    letter-spacing: 0.02em;
    margin-top: 30px;
    margin-bottom: 40px;
}

@media only screen and (max-width: 840px) {
    .modal-content {
      width: 100%;
      height: 100%;
    }
}

@media only screen and (max-height: 800px) {
    .modal-content {
      height: 100%;
    }
    .modal-body {
      max-height: 95%;
      overflow-y: auto;
    }

    .additions {
        width: 280px;
        margin: 0 auto;
        padding-top: 20px;
    }


}
</style>