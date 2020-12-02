<template>
  <div class="names">
    <ul>
      <li v-for="(name, index) in data" :key="index" v-bind:class="{ even: index%2 !== 0 }"><input :id="name + index" class="checkbox" :value="name" type="checkbox" v-model="checkedEl" @change="change()"><label :for="name + index">{{name}}</label></li>
    </ul>
   </div>
</template>

<script>
export default {
    data() {
        return {
            checkedEl: []
        }
    },
    mounted() {
        this.checkedEl = this.checkedItems;
    },
    props: {
        data: Array,
        checkedItems: Array
    },
    methods: {
        change() {
            this.$emit("update:checkedItems", this.checkedEl);
        }
    }
}
</script>

<style scoped>
 .names {
    width: 90%;
    height: 100%;
    max-height: 250px;
    overflow-y: scroll;
    border: 1px solid rgba(0,0,0,.2);
    border-radius: 6px;
    margin: 0 auto;
    padding-top: 10px;
  }
  li {
    list-style-type: none;
    padding: 5px 20px;
  }
  li:hover {
    background-color: #F1EDE9;
  }
  ul {
    text-align: left;
    padding-left: 0;
  }
  .even {
      background-color: #f8f6f4c7;
  }
  label {
    margin-bottom: 2px;
    cursor: pointer !important;
    font-family: Montserrat;
    font-style: normal;
  }
  .checkbox {
    transform: scale(1.4);
    display: inline-block;
    margin-right: 10px;
  }
</style>