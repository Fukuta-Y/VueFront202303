<template>
  <TitileMidashi
  />
  <SearchJoken 
    @on-search-joken="onSearchJoken"
  />
  <HosokuSetsumei/>
</template>

<script>
import TitileMidashi from './components/TitileMidashi.vue'
import SearchJoken from './components/SearchJoken.vue'
import HosokuSetsumei from './components/HosokuSetsumei.vue'

export default {
  name: 'SearchJokenBaseForm',
  components: {
    TitileMidashi,
    SearchJoken,
    HosokuSetsumei
  },
  data() {
    return {
      searchJoken: {},
    }
  },
methods: {
    onSearchJoken(data) {
      this.searchJoken = data
      this.$router.push({ name: 'SearchListBaseForm', params: { name: this.searchJoken.name, seibetsu: this.searchJoken.seibetsu, address: this.searchJoken.address, }, })
    }
  },
}
</script>
<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
