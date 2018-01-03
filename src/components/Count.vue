<template>
  <div>
    <h2>{{msg}}</h2>
    <hr/>
    <!-- <h3>{{$store.state.count}}-{{count}}</h3> -->
    <h3>{{$store.state.a.count}}-{{count}}</h3>
    <p>
      <!-- <button @click="add">+</button>
      <button @click="reduce">-</button> -->
      <button @click="addAction">+</button>
      <button @click="reduceAction">-</button>
    </p>
  </div>
</template>
<script>
import store from '@/vuex/store'
import { mapState, mapMutations, mapGetters, mapActions } from 'vuex'
export default {
  data () {
    return {
      msg: 'Hello Vuex'
    }
  },
  // computed: {
  //   count () {
  //     return this.$store.state.count
  //   }
  // },
  // computed: mapState(['count']),
  // computed: {
  //   ...mapState(['count']),
  //   ...mapGetters(['count'])
  // },
  computed:{
    count(){
        return this.$store.state.a.count;
    },
    ...mapGetters(['count'])
  },
  methods: {
    ...mapMutations([
      'add', 'reduce'
    ]),
    ...mapActions(['addAction', 'reduceAction'])
  },
  store
}
</script>
