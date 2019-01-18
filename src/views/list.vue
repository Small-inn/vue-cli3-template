<template>
    <div class="list">
        <scroll class="wrapper"
                @scroll="scroll"
                :list="data"
                :pullDown="pulldown"
                @pullingDown="loadData"
                :pullUpLoad="pullup"
                @pullingUp="pullingUp">
            <ul class="content" slot="content">
                <li class="item" v-for="(item, index) in data" :key="index">{{item}}</li>
            </ul>
        </scroll>
    </div>
</template>

<script>
import scroll from '@/components/scroll.vue'
const list = [1, 2, 3, 4, 5, 5, 5, 5, 6, 645, 22]
export default {
  components: {
    scroll
  },
  data () {
    return {
      pulldown: true,
      pullup: true,
      data: list
    }
  },
  created () {},
  methods: {
    scroll (pos) {
      // console.log(pos);
    },
    loadData () {
      // debugger
      // alert(1)
    },
    pullingUp () {}
  }
}
</script>

<style lang="stylus" scoped>
.list
    width 100%
    height 100%
    .wrapper
        position relative
        width 100%
        height 500px
        overflow hidden
        background-color #ccc
        .list-wrapper
            .content
                width 100%
                .item
                    height 50px
                    line-height 50px
</style>
