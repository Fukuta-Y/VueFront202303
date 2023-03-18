<template>
  <div>
    <table align="center">
      <tr>
        <td>お名前： </td>
        <td><input type="text" v-model="name" size="30" placeholder="○○太郎"></td>
      </tr>
      <tr>
        <td>性別：</td>
        <td>
          <input type="radio" name='seibetsu' value="1" v-model="seibetsu"/>
          <label>男</label>
          &nbsp;&nbsp;&nbsp;
          <input type="radio" name='seibetsu' value="2" v-model="seibetsu"/>
          <label>女</label>
        </td>
      </tr>
      <tr>
        <td>ご住所： </td>
        <td><input type="text" v-model="address" size="30" placeholder="東京都○○区"></td>
      </tr>
    </table>
    <br>
    <button 
      v-on:click="btnClear()">
      クリア
    </button>
    &nbsp;&nbsp;&nbsp;
    <button v-on:click="btnSearch()">
      検索
    </button>
    <br>
    <br>
  </div>
</template>

<script>
export default {
  name: 'SearchJoken',
  props: {
  },
  data() {
    return {
      name: '',
      address: '',
      seibetsu: '',
      searchJoken:{
        name: '',
        seibetsu: '',
        address: '',
      },
    }
  },
  mount() {
    this.init();
  },
  methods: {
    btnSearch() {
      this.searchJoken.name = this.name
      this.searchJoken.address = this.address
      this.searchJoken.seibetsu = this.seibetsu
      this.$emit('onSearchJoken', this.searchJoken)
    },
    btnClear() {
      this.init();
    },
    init(){
      this.name = ''
      this.address= ''
      this.seibetsu = ''
    }
  },
}
</script>
<style scoped>
</style>
