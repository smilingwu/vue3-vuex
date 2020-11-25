<template>
  <div>
    <div class="item">当前数量是{{count}} <button @click="add">增加</button></div>
    <button @click="asyncAdd">异步操作+10</button>
  </div>
</template>

<script>
import {mapMutations} from "vuex";
export default {
  data () {
    return {

    }
  },
  computed: {
    count () {
      //return this.$store.getters.getCount
      return this.$store.state.Counter.count
    }
  },
  methods: {
    add () {
      this.$store.commit('Counter/add', 1)
    },
    asyncAdd () {
      setTimeout(() => {
        this.$store.dispatch('Counter/asyncAdd', 10)
      }, 1000)
    }
  }
}
</script>
<style lang='less' scoped>
.herox{
  width: 100%;
  background: url(https://ws1.sinaimg.cn/large/006tNbRwgy1fw36zy9fysj313t0me0xj.jpg)no-repeat;
  background-size: 100% 100%;
  background-position: center;
  height: 100vh;
  margin: 0px;
  padding: 0px;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 14px;
  color: #000;
}
</style>