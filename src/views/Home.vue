<template>
  <div class="home">
   <marquee-self></marquee-self>
   <div class="node" @click="go">走你</div>
   <div class="node" @click="come">来了，老弟</div>
  </div>
</template>

<script>
// @ is an alias to /src
import Marquee from '@/components/marquee.vue'

export default {
  name: 'home',
  components: {
    'marquee-self': Marquee
  },
  mounted () {},
  data () {
    return {}
  },
  methods: {
    // 跳转
    go () {
      this.$router.push({ path: '/about' })
    },
    come () {
      this.$router.push({ path: '/list' })
    }
  }
}
</script>
<style scoped>
  .node {
    border: 1px solid #000;
    margin-top: 20px;
  }
</style>
