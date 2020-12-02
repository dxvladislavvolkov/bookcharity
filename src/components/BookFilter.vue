<template>
  <div class="filter">
      <button type="button" class="btn btn-secondary filter-button" @click="openFilter($event)"><i class="fas fa-filter"></i> Фильтр</button>
      <div v-if="isOpened" class="filter-content">
        <div class="filter-block">
          <h4 class="filter-name">Город:</h4>
          <List :data="cities" v-model:checkedItems="checkedCities" />
        </div>
        <div class="filter-block">
          <h4 class="filter-name">Язык:</h4>
          <List :data="langs" v-model:checkedItems="checkedLang" />
        </div>
        <div class="filter-block">
          <h4 class="filter-name">Авторы:</h4>
          <List :data="authors" v-model:checkedItems="checkedNames" />
        </div>
        <button  type="button" class="btn btn-secondary apply-filter" @click="applyFilter">Применить</button>
      </div>
  </div>
</template>

<script>
import List from "./List";

export default {
  components: {
    List
  },
  data() {
    return {
      isOpened: false,
      allowOutsideClick: false,
      checkedNames: [],
      checkedLang: [],
      checkedCities: []
    }
  },
  props: {
    authors: Array,
    langs: Array,
    cities: Array
  },
  created: function() {
    window.addEventListener("click",this.ClickOutside);
  },
  unmounted: function() {
    window.removeEventListener("click", this.ClickOutside);
  },
  methods: {
    openFilter() {
      this.isOpened = !this.isOpened;
    },
    applyFilter() {
      this.$emit("apply-filter", {
        checkedNames: this.checkedNames,
        checkedLangs: this.checkedLang,
        checkedCities: this.checkedCities
      });
      this.isOpened = false;
    },
    ClickOutside(e) {
      if(this.$el === e.target || !this.$el.contains(e.target) ) {
        this.isOpened = false;
      }
    }
  }
}
</script>

<style scoped>
  .filter-block {
      margin: 17px 0;
  }

  .filter-button{
    width: 150px;
    height: 56px;
    border: 1px solid;
    color: #A38970 !important;
    background-color: #fff;
  }
  .apply-filter {
    width: 150px;
    height: 50px;
    margin: 10px 0;

    background-color: #A38970 !important;
    color: #fff;
  }
  .filter-name {
    text-align: left;
    margin-left: 5%;
    font-family: Montserrat;
    font-size: 16px;
    font-style: normal;
    font-weight: 600;
    line-height: 20px;
    letter-spacing: 0.05em;
  }

  .filter {
    position: relative;
    display: inline-block;
  }
  .btn {
    font-family: Montserrat;
    font-size: 16px;
    font-style: normal;
    font-weight: 700;
    line-height: 20px;
    letter-spacing: 0.02em;
}

.btn-secondary, .btn-secondary:hover, .btn-secondary:active, .btn-secondary:visited {

}

.filter-content {
  display: block;
  position: absolute;
  background-color: #fff;
  background-clip: padding-box;
  border: 1px solid rgba(0,0,0,.2);
  border-radius: 6px;
  min-width: 500px;
  overflow-y: auto;
  max-height: 500px;
  -webkit-box-shadow: 0 3px 9px rgba(0,0,0,.5);
  box-shadow: 0 3px 9px rgba(0,0,0,.5);
  z-index: 1;
}
@media only screen and (max-width: 840px) {
    .filter-content {
      position: fixed;
      left: 50%;
      top: 50%;
      transform: translate(-50%,-50%);
      overflow-y: auto;
      height: 100%;
      min-width: 100%;
      max-width: 100%;
      max-height: 100%;
    }
}
</style>