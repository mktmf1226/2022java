<template>
  <div>
    <!-- 1) $event : 현재 시점에서 발생한 이벤트값 -->
    <input type="search" @keyup="checkEnter($event)" v-model="searchText">
    <hr>
    <!-- 2) 1)의 다른 방법. keyup이벤트이 세부 속성들 -->
    <!-- .enter -->
    <!-- .tab -->
    <!-- .delete -->
    <!-- .space -->
    <!-- .ctrl.enter -->
    <input type="search" @keyup.enter="doSearch" v-model="searchText">
    <button @click="doSearch">조회</button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      searchText: ''
    }
  },
  methods: {
    doSearch() {
      alert(this.searchText)
    },
    checkEnter(event) { // 변수 명은 아무거나 써도 된다
      // alert(event)
      if (event.keyCode === 13) { // 13은 Enter 키의 키값이다.
        // alert()
        this.doSearch()
      }
    }
  }
}
</script>
