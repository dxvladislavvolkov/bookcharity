<template>
  <div class="toolbar">
      <div class="left-side">
          <BookFilter :authors="filterData.authors" :cities="filterData.cities" :langs="filterData.langs" @applyFilter="onApplyFilter($event)"></BookFilter>
      </div>
  </div>
</template>

<script>
import BookFilter from "./BookFilter";
export default {
    components: {
        BookFilter
    },
    props: {
        filterData: Object
    },
    methods: {
        onApplyFilter(e) {
            this.$emit("apply-filter", e);
        }
    }
}
</script>

<style scoped>
    .toolbar {
        display: flex;
        align-items: center;
        margin: 0 10% 80px 10%;
    }
    @media only screen and (max-width: 840px) {
    .left-side {
      margin: 0 auto;
    }
}
</style>