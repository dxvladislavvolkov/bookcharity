<template>
  <div class="modal-content" v-if="visible">
    <div>
      <i class="custom-icon fas fa-times fa-lg" @click="onClose"></i>
    </div>
    <div class="title text">{{data.author}}</div>
    <div class="name text">{{data.name}}</div>
    <div>
      <img src="../assets/book.jpg" />
    </div>
    <div>{{data.description}}</div>
    <button type="button" class="btn btn-secondary" @click="onClick">Написать @maggvlk</button>
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
    left: 0;
    right: 0;
    margin-left: auto;
    margin-right: auto;
}

.modal-content div:first-child {
  text-align: right;
  padding: 20px;
}

i {
  cursor: pointer;
}

img {
  width: 280px;
  margin-top: 25px;
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
      z-index: 1001;
      width: 100%;
      height: 100%;
      position: fixed;
      top: 0;
      margin-left: 0;
      margin-right: 0;
    }
}
</style>