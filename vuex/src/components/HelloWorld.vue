<template>
  <div>
    <button @click="increment">+</button>
    <button @click="addCount">10</button>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    msg: String
  },
  methods:{
    /* increment(){
      // mutationsの場合はcommitでmutations呼び出し
      this.$store.commit('increment')
    },

    addCount(){
      this.$store.commit('addCount', {
        value: 10
      })
    } */
    increment(){
      // actionはdispatch
      this.$store.dispatch('incrementAction')
    },
    addCount(){
      this.$store.dispatch('addCountAction', {
        // payloadに10が入る
        value: 10
      })
    }
  }
}
</script>