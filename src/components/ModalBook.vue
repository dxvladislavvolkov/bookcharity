<template>
  <div class="modal-content" v-if="visible">
    <div class="title"></div>
    SomeContent
  </div>
</template>

<script>
export default {
    props: {
        visible: Boolean
    }
}
</script>

<style>
.modal-content {
    width: 40%;
    height: 400px;
    background-color: aqua;
    position: fixed;
    left: 0;
    right: 0;
    margin-left: auto;
    margin-right: auto;
    min-width: 320px;
}
</style>