<template>
    <div class="marquee-wrap">
        <div class="wrap">
            <div class="box" id="box">
            <div class="marquee" id="marquee">{{text}}</div>
        </div>
   </div>
    </div>
</template>
<script>
export default {
  props: {
    list: {
      type: Array,
      default: () => {
        return ['王老师说这款商品太不好了，打十分开奖号法律框架', '李师傅说保温杯不好用，快递太慢了卡了康师傅喝茶']
      }
    }
  },
  mounted () {
    this.list.map(item => { this.text += ' ' + item })
    console.log(this.text)
    // this.move();
  },
  updated () {
    this.move()
  },
  data () {
    return {
      text: ''
    }
  },
  methods: {
    move () {
      let width = document.getElementById('marquee').getBoundingClientRect().width
      let box = document.getElementById('box')
      console.log(width)
      let distance = 375
      let timer = null
      timer = requestAnimationFrame(function fn () {
        distance -= 1
        timer = requestAnimationFrame(fn)
        if (-distance >= width) {
          distance = 375
        }
        box.style.transform = `translateX(${distance}px)`
      }, 40)
    }
  }
}
</script>
<style scoped>
  .wrap {
    overflow: hidden;
    color: #005bbe;
  }
  .box{
    width: 500%;
    height: 100%;
  }
  .box .marquee {
    float: left;
    /* margin: -5px 16px 0 20px; */
  }
  .node {
    margin-top: 20px;
    border: 1px solid #000;
  }
</style>
